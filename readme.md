# App Deployment
## ☁️ Cloud Intro
`Cloud Computing` is the on demand delivery, with access to what you need concerning computing resources, eg, processes,networking, applications, etc, which can be accessed via the internet, making it accessible anywhere.

`Cloud Deployment Models` can be split into  *simple* and *complex* models.


| Simple | Complex |
|:-------| :-------|
| Public - Shared Tenancy | Hybrid - Public + Private |
| Private - Single or Sole Tenancy | Multi - Combining multiple providers |


- **Simple** models can be public, which have a shared tenancy with different clients or private where a client may have a single or sole tenancy.

- **Complex** models can be hybrid, which can be made up with a public and private model or a Multi-Cloud, which can be made up of different cloud providers.


`Cloud Service Types` are services that cloud providers offer.  Some services offered are IaaS (Infastructure as a Service), PaaS (Platform as a Service), SaaS (Software as a Service), FaaS (Function as a Service) and many more.


## 🔐 SSH and SSH Key Pairs

- **SSH** - stands for 'Secure Shell'.  This ensures that a secure 'tunnel' is created to login remotely from one computer to another.

- **SSH Key Pairs** - are secure keys consisting of a `public key` and a `private key` used to authenticate a user's credentials.


## 🖥️ Virtual Machines
After logging into AWS, user should navigate to the EC2 page, that can be found by entering EC2 in the search bar or using the menu bar.

Before creating an instance, the user should create a Key Pair by selecint the `Key Pair` option in the menu.

Enter a valid name for your key pair that will be relevant to what you plan to use it for. After creating it, download and save your `private key` to the `.ssh` file that can be found or created in the in the user's directory. 

After saving the private key, click on the `Instances` option that can be found in the menu.  On the `Instances` page, click on the `Instances` button and do the following:

- Name - In the 'Name' field, enter a valid and relevant name for the instance you are about to launch.
- Application Get application image (Free tier) - Choose the application (OS) you need for your project.
- Key pair - Select the key pair you created earlier to link to this instance.
- Network settings ( Use existing security group already created) - Create settings needed for your instance or if you have already save a security group, select the `Use Existing security group` opton.
- Double check the instance details and launch.  When successful, you will get a green banner explaining that it is running.
- Make your way to the summary page, that is where all the information needed will be displayed.

## 💻 EC2 Deployment
To deploy your instance do the following:

- On the *Instance summary page* click the `Connect` button
- If this is the first time to use your `private key` it will recommend to change the permission to 'Owner read only' (chmod 400 "*keyname.pem*") - *change keyname.pem to the name of your saved private key*.
- Open a `Git Bash` CLI (Command Line Interface), copy the `Example` option to login.  Since it is the first time to login, using the credetials, it will display a question 'Are you sure  you want to continue connecting (yes/no/[fingerprint])? Enter 'yes' to continue.
- After successully login into the instance remotely, update all appls by running the following command: 
    ```bash 
    sudo apt update -y
    ```

- After updating, since it is the first time of using this, it is recommend to upgrade all applications using the following command: 
    ``` bash
    sudo apt upgrade -y
    ```
- **Install nginx** - To install a server, in this case 'nginx' enter the following command: 
    ```bash
    sudo apt install nginx -y
    ```
    the '-y' will answer any question that arises during installtion to 'yes'

- After installing `nginx`, to check if it is running enter the command: 
    ```bash
    systemctl status nginx
    ```
- On the `Summary` page, copy `Public ipv4 address` to view nginx.
