  <summary>Export Shared Mailboxes Script</summary>

  ```powershell
  # Connect to Exchange Online (if using Exchange Online)
  # Remove this section if using on-prem Exchange
  $UserCredential = Get-Credential
  Connect-ExchangeOnline -UserPrincipalName $UserCredential.UserName -ShowProgress $true

  # Get all shared mailboxes
  $sharedMailboxes = Get-Mailbox -RecipientTypeDetails SharedMailbox

  # Create an array to store the results
  $sharedMailboxList = @()

  # Loop through each shared mailbox and retrieve information
  foreach ($mailbox in $sharedMailboxes) {
      # Get the mailbox name and aliases
      $name = $mailbox.DisplayName
      $aliases = $mailbox.EmailAddresses | Where-Object { $_ -like "SMTP:*" } | ForEach-Object { $_.Substring(5) }

      # Get the members (full access users)
      $members = Get-MailboxPermission -Identity $mailbox.Identity | Where-Object { $_.AccessRights -contains "FullAccess" } | ForEach-Object { $_.User }

      # Add the mailbox information to the array
      $sharedMailboxList += [pscustomobject]@{
          Name    = $name
          Aliases = ($aliases -join ", ")
          Members = ($members -join ", ")
      }
  }

  # Export the results to a CSV file
  $sharedMailboxList | Export-Csv -Path "C:\SharedMailboxes.csv" -NoTypeInformation

  # Disconnect from Exchange Online (if applicable)
  Disconnect-ExchangeOnline -Confirm:$false
