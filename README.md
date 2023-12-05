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
   4. You can now access your entire server vm via VSCode, and your explorer in VSCode should resemble the following:

      ![vscode-explorer-first-time-connect-ssh](./img/vscode-explorer-first-time-connect-ssh.png)
8. Download `docker` from <https://get.docker.com> as follows:

   ```sh
   # Download Docker Script
   sudo curl -fsSL https://get.docker.com -o install-docker.sh

   # Do a dry-run (optional)
   sudo sh install-docker.sh --dry-run

   # Install Docker
   sudo sh install-docker.sh

   # Add the current user to 'docker' group
   sudo usermod -aG docker ${USER}

   # Use docker and check running containers
   docker ps # this command won't work unless the user is `sudo`
   ```

</details>

<details>
<summary>

### DevOps LifeCycle ♻️

</summary>

![devops-lifecycle](https://cacoo.com/wp-app/uploads/2021/06/continuous-development-visual.png)

- `Plan` & `Code` together is known as `Continuos Development`,
- `Build` & `Test` together is known as `Continuos Integration` &mdash; sometimes also called _Heart of DevOps_,
- `Release` & `Deploy` together is known as `Continuous Deployment`, and
- `Operate` & `Monitor` together is known as `Continuos Monitoring`.

`Continuos Monitoring` is considered the most crucial stage in the DevOps LifeCycle as in this stage we can check if the system is running in accordance to the standards that are expected by the end-users, and here's where we can check the health of the system and application performance.

With these valuable metrics, we are then able to add further benefit to the overall performance to our environment such as reducing support costs, improving productivity, and increasing system reliability, and from the analytics and reporting generated from the `monitoring` stage, we can have a clear vision for further planning of development of the application and system.

`Monitoring` has the following 5 stages:

![monitoring-stages-devops](./img/devops-monitoring-stages.png)

</details>
