## Form fields ##

- Project name
- Description
- Mail
- SSH keypair
- Validity
- Flavor
- Heat Template

# Parameters properties #

Project name:
- Mandatory
- Textbox
- Heat: Stack Name

Description:
- Facultative
- Textbox
- Stored in stack metadata

Mail:
- Mandatory
- Textbox
- Used to send notifications
- Stored in stack metadata

SSH keypair:
- Facultative
- Textbox
- If given, imported in OpenStack, else a new one is generated
- Must be generated using Nova API in Havana, directly from Heat with IceHouse

Validity:
- Mandatory
- Slider of N days
- Used by scripts to send notifications or removed expired stacks

Flavor:
- Mandatory
- Droplist
- Auto-generated from Nova data (nova.flavors.list)
- Shows vCPUs and Memory
- Can accept filter from config (used to hide some flavors)

Heat Template:
- Mandatory
- Droplist
- Auto-generated from heat templates directory
- Title is generated from filename
- Description is taken from the YAML

# Metadata Fields #

- Description
- Mail
- Validity

# Heat parameters #

- Project name
- SSH keypair
- Flavor
- Heat Template
