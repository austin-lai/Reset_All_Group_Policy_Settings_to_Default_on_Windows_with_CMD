
# Reset All Group Policy Settings to Default on Windows with CMD

```markdown
> Austin.Lai |
> -----------| September 25th, 2023
> -----------| Updated on September 25th, 2023
```

---

## Table of Contents

<!-- TOC -->

- [Reset All Group Policy Settings to Default on Windows with CMD](#reset-all-group-policy-settings-to-default-on-windows-with-cmd)
    - [Table of Contents](#table-of-contents)
    - [Disclaimer](#disclaimer)
    - [Description](#description)

<!-- /TOC -->

<br>

## Disclaimer

<span style="color: red; font-weight: bold;">DISCLAIMER:</span>

This project/repository is provided "as is" and without warranty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose and noninfringement. In no event shall the authors or copyright holders be liable for any claim, damages or other liability, whether in an action of contract, tort or otherwise, arising from, out of or in connection with the software or the use or other dealings in the software.

This project/repository is for <span style="color: red; font-weight: bold;">Educational</span> purpose <span style="color: red; font-weight: bold;">ONLY</span>. Do not use it without permission. The usual disclaimer applies, especially the fact that me (Austin) is not liable for any damages caused by direct or indirect use of the information or functionality provided by these programs. The author or any Internet provider bears NO responsibility for content or misuse of these programs or any derivatives thereof. By using these programs you accept the fact that any damage (data loss, system crash, system compromise, etc.) caused by the use of these programs is not Austin responsibility.

<br>

## Description

<!-- Description -->

Reset All Group Policy Settings to Default on Windows with CMD

Windows stores local Group Policy settings in the `Registry.pol`` files. The policy settings for the user and the computer are stored in separate POL files.

The computer settings (Computer Configuration section) are stored in `%SystemRoot%\System32\GroupPolicy\Machine\registry.pol`

The user settings (User Configuration section) are stored in `%SystemRoot%\System32\GroupPolicy\User\registry.pol`

```batch
@REM "RD" = Removes (deletes) a directory.
RD /S /Q "%WinDir%\System32\GroupPolicyUsers" && RD /S /Q "%WinDir%\System32\GroupPolicy" 

gpupdate /force
```

OR

```batch
RD /S /Q "%WinDir%\System32\GroupPolicyUsers"
RD /S /Q "%WinDir%\System32\GroupPolicy"

gpupdate /force
```

<!-- /Description -->

<br>
