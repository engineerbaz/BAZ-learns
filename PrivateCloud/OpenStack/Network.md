# Network

Metadata Agent 🕵️ is one of the unsung heroes of OpenStack.It sits inside the Neutron 🔌 network namespace and "intercepts" requests sent to that magic IP ($169.254.169.254$). It then reaches out to the Nova 🖥️ API to fetch the specific details for that VM (like its hostname or SSH keys) and passes them back. Without this, your VMs would boot up but wouldn't know who they are!
