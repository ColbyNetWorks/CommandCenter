## Table of Contents

1. [Phonetic Alphabet](#phonetic-alphabet)
2. [Microsoft Deployment Toolkit (MDT)](#microsoft-deployment-toolkit-mdt)
3. [Export Shared Mailboxes Script](#export-shared-mailboxes-script)

---

<details>
  <summary>Phonetic Alphabet</summary>

  | **Letter** | **Phonetic Word** | **Letter** | **Phonetic Word** |
  |------------|-------------------|------------|-------------------|
  | A          | Alpha             | N          | November          |
  | B          | Bravo             | O          | Oscar             |
  | C          | Charlie           | P          | Papa              |
  | D          | Delta             | Q          | Quebec            |
  | E          | Echo              | R          | Romeo             |
  | F          | Foxtrot           | S          | Sierra            |
  | G          | Golf              | T          | Tango             |
  | H          | Hotel             | U          | Uniform           |
  | I          | India             | V          | Victor            |
  | J          | Juliett           | W          | Whiskey           |
  | K          | Kilo              | X          | X-ray             |
  | L          | Lima              | Y          | Yankee            |
  | M          | Mike              | Z          | Zulu              |

</details>

---

<details>
  <summary>Microsoft Deployment Toolkit (MDT)</summary>

  ### What is MDT?
  The **Microsoft Deployment Toolkit (MDT)** is a solution accelerator from Microsoft used for automating the deployment of Windows operating systems and applications. It helps administrators perform both bare-metal and upgrade deployments for desktops, laptops, and servers. MDT provides an easy-to-use framework for imaging, deployment, and configuration of Windows, making the setup process easier and more efficient for IT departments.

  ### Download MDT:
  You can download the latest version of the Microsoft Deployment Toolkit from the official Microsoft website:  
  [Download MDT](https://www.microsoft.com/en-us/download/details.aspx?id=54259)

  ### Example MDT Script:
  
  ```powershell
  # Install MDT
  Import-Module "C:\Program Files\Microsoft Deployment Toolkit\Bin\MicrosoftDeploymentToolkit.psd1"

  # Deploy an Operating System using MDT
  New-PSDrive -Name "MDT" -PSProvider FileSystem -Root "\\server\MDTDeploymentShare"
  Set-Location -Path "MDT:\"

  # Specify the task sequence to run
  $TaskSequence = "Deploy Windows 10"

  # Run the deployment
  Start-Process "C:\DeploymentShare\Scripts\LiteTouch.vbs" -ArgumentList "/tasksequence:$TaskSequence"
```
</details>
