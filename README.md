# Monitoring &mdash; Prometheus & Grafana

Welcome to the [Monitoring &mdash; Prometheus & Grafana](#monitoring--prometheus--grafana) repository! Explore hands-on exercises/concepts and configuration examples to understand monitoring with Prometheus and Grafana. Find documentation to guide your learning journey. 🚀📊

![moving-charts-gif](https://media.licdn.com/dms/image/C5612AQGvgZ3yDchrvg/article-cover_image-shrink_720_1280/0/1593057704922?e=1707350400&v=beta&t=fyMtK7q5m252qzvoZfyaui38GCTw1G392IwI0w5vqe0)

<details>
<summary>

## Setup & Installation 🔧💻

</summary>

1. Download [VirtualBox](https://www.oracle.com/in/virtualization/technologies/vm/downloads/virtualbox-downloads.html) (or follow instructions to [install virtual box in ubuntu](https://tecadmin.net/install-virtualbox-on-ubuntu-20-04/))
2. Download [Ubuntu Server Image `18.04`](https://releases.ubuntu.com/18.04/).
3. Open Virtual Box and allocate 10GB fixed disk, 2 CPUs, and mount the image as Bridge (adapter) in the Network tab.
4. Now while installing Ubuntu Server, make sure to install `OpenSSH` (and installing `prometheus` is optional).
5. Once installation is completed and you're logged in to your user (note down the IP for remote access), just update and upgrade your vm:

   ```sh
   sudo apt-get update && sudo apt-get upgrade
   ```

6. Before the next step, `poweroff` the vm and start the ubuntu server vm in headless mode.
7. Download, Install, and Open [VSCode](https://code.visualstudio.com/download):
   1. Install the [`Remote SSH`](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-ssh) extension from Microsoft.
   2. `Ctrl + Shift + P` and type in `Remote-SSH: Add new SSH Host...`, and click on the option. A prompt for username and IP will be asked where you've to type in:

      ```sh
      ssh <username>@<ubuntu-server-ip> # make sure the ubuntu server vm is started in headless mode
      ```

   3. Choose a configuration file for configuring SSH keys and then the `Remote-SSH` extension will prompt for password, once you type it in, a dialog to `Confirm` will be asked where you've to click `Confirm` to connect to the vm via VSCode.
   4. You can now access your entire server vm via VSCode, and your explorer in VSCode should resemble the following: ![vscode-explorer-first-time-connect-ssh](./img/vscode-explorer-first-time-connect-ssh.png)

</details>
