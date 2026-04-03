<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Set Up a Web App in the Cloud

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-devops-vscode)

**Author:** Shahid Sayed  
**Email:** shahidsayed399@gmail.com

---

## Set Up a Web App Using AWS and VS Code

![Image](http://learn.nextwork.org/exuberant_orange_gentle_water_snake/uploads/aws-devops-vscode_7a1de541)

---

## Introducing Today's Project!

This project is the first task of my 7-day DevOps challenge. In this project, I am setting up the foundation of a CI/CD pipeline by creating a web application from scratch. I will launch an AWS EC2 instance and connect it to VS Code using a remote development setup to configure and prepare the application environment. The objective of this project is to build hands-on understanding of AWS infrastructure and CI/CD workflow fundamentals.

This project is part one of a series of DevOps projects where I’m building a CI/CD pipeline, and I’ll be working on the next project later this weekend.

I did this project to gain hands-on experience working with a Java-based web application on a remote server and to improve my understanding of how developers manage and edit application files directly through the terminal. It is also the first project in the DevOps challenge where we start building the foundation for a full CI/CD pipeline, and the upcoming projects will continue building on this same setup. This makes it an important base for learning real-world workflows using tools like Maven on environments such as Amazon Elastic Compute Cloud instances.

### Key tools and concepts

Services I used were Amazon Elastic Compute Cloud (EC2) to host and access the remote server environment, along with Java and Maven to build and run the web application project.

Key concepts I learnt include navigating directories using terminal commands, editing files directly on a remote server using nano, understanding the structure of a Maven-based web application project, and working with index.jsp files to create dynamic web content without relying only on an IDE.

### Project reflection

This project took me approximately 3.5 hours to complete from setting up the environment to editing and verifying the application files on the server. The most challenging part was navigating the project structure and editing the index.jsp file directly from the terminal instead of using an IDE. It was most rewarding to successfully make changes through the terminal and verify them in the SSH remote window, which helped me better understand how web applications are managed on remote servers like Amazon Elastic Compute Cloud instances.

One thing I didn’t expect in this project was how easy it was to edit application files directly from the terminal without using an IDE and still see the changes immediately in the remote environment. It helped me understand how developers can manage and update applications directly on servers like Amazon Elastic Compute Cloud instances in real-world cloud workflows

---

## Launching an EC2 instance

### What I did in this step

In this step, I will launch an EC2 instance in my AWS account and configure its network settings. This helps ensure that the EC2 instance can be accessed properly over the network. I will also create and use a key pair, which provides secure permission to connect to the EC2 instance.

I started this project by launching an EC2 instance because EC2 instances are like virtual computers that run in the cloud. Since I want my web application to be hosted entirely in the cloud, I launched an EC2 instance where I will set up and run my web application.

![Image](http://learn.nextwork.org/exuberant_orange_gentle_water_snake/uploads/aws-devops-vscode_7852fbf3)

### I also enabled SSH

SH (Secure Shell) is a protocol used to securely connect to a remote server. It ensures that only authorized users can access the server. I enabled SSH access so that I can connect to my EC2 instance later. SSH verifies that the private key on my local system matches the public key stored on the EC2 instance before allowing access.

### Key pairs

A key pair is used to securely connect to your EC2 instance, which acts like a virtual computer in the cloud. It allows you to access the instance remotely using SSH. A key pair consists of two keys: a public key and a private key. AWS stores the public key on the EC2 instance, and you keep the private key on your local machine to securely connect to the instance.

### Downloaded key pair file

After creating the key pair, AWS automatically downloaded a .pem file to my local machine. This file represents the private key and is required to securely connect to the EC2 instance using SSH. It acts as an authentication method to verify access to the instance.

---

## Set up VS Code

### What I did in this step

In this step, I will download and install VS Code on my computer, which I will use to write and edit code. I will also set up the terminal in VS Code so that I can communicate with my EC2 instance remotely. Additionally, I will configure the required permission settings so that I can securely log in to my EC2 instance later using SSH.

### What is VS Code?

VS Code (Visual Studio Code) is a lightweight and popular Integrated Development Environment (IDE) used for writing, editing, and managing code. It also provides features like an integrated terminal, extensions, and remote development support, which help in working with cloud-based servers such as EC2 instances. 

I installed VS Code to write and manage my web application code. It also includes useful features like an integrated terminal and remote development extensions, which allow me to connect to virtual servers such as EC2 instances and work on them directly from my local system.

![Image](http://learn.nextwork.org/exuberant_orange_gentle_water_snake/uploads/aws-devops-vscode_53d05e68)

---

## My first terminal commands

A terminal is a command-line interface used to interact with the computer by typing text commands instead of using the graphical user interface (GUI). It allows users to execute commands efficiently and manage files and systems. The first command I ran for this project was cd ~\Desktop\DevOps, which changed the working directory of the terminal to the DevOps folder located on my Desktop.

### Updating file permissions

I changed the file permissions of my .pem key file using the icacls command in PowerShell. I removed inherited permissions and granted read-only access to my user account. This ensures that only my user can access the private key file, which is required for secure SSH authentication when connecting to the EC2 instance.

![Image](http://learn.nextwork.org/exuberant_orange_gentle_water_snake/uploads/aws-devops-vscode_9328ada1)

---

## SSH connection to EC2 instance

### What I did in this step

In this step, I will connect to the EC2 instance so that I can start setting up my web application code inside the server.

### Connecting to EC2

To connect to my EC2 instance, I used the SSH command with my private key file, the EC2 user, and the instance’s public DNS address. This established a secure remote connection between my local system and the EC2 instance, allowing me to configure the server and set up my web application environment.

### This command required an IPv4 address

The IPv4 Public DNS of an EC2 instance is a public address assigned by AWS that allows the instance to be accessed over the internet. It is useful for connecting from my local computer to the EC2 instance remotely using SSH, as it tells the system where to locate the running instance in the cloud.

![Image](http://learn.nextwork.org/exuberant_orange_gentle_water_snake/uploads/aws-devops-vscode_e3069dca)

---

## Maven & Java

### What I did in this step

In this step, I will install Java and Maven on my EC2 instance because both tools are essential for setting up a Java web application from scratch. Java provides the runtime environment needed to run the application, while Maven is used to manage project dependencies and automate the build process.

### Why I'm using Maven

Apache Maven is tool that helps developers build and organize Java software projects. It's also a package manager, which means it automatically download any external pieces of code your project depends on to work.

Maven is required in this project because it's really useful for kick-starting web projects! It uses something called archetypes, which are like templates, to lay out the foundations for different types of projects e.g. web apps.

### Why I'm using Java

Java is a popular programming language used to build different types of applications, from mobile apps to large enterprise systems.

Java is required in this project because maven NEEDS Java to operate. So if we don't install Java, we won't be able to use Maven to generate/build our web app today.


---

## Create the Application

### What I did in this step

In this phase, I will configure the application on the EC2 instance by running Maven commands in the terminal to generate the Java application on the instance.

### Creating the Java web app

I generated a Java web application using the command
mvn archetype:generate -DgroupId=com.nextwork.app -DartifactId=nextwork-web-project -DarchetypeArtifactId=maven-archetype-webapp -DinteractiveMode=false.
This command instructs Maven to create a new web application using an existing template (archetype) and assigns the project the name nextwork-web-project.

### Installing Remote - SSH

I installed the Remote – SSH extension in VS Code, which allows me to connect VS Code directly to a remote server such as an EC2 instance. I installed this extension to enable remote development and to access my EC2 instance with full IDE features like file editing, navigation, and extension support directly from VS Code.

### SSH configuration details

The configuration details required to set up a remote connection include the host (the EC2 instance address), the identity file (the location of the private key used for authentication), and the user (the username used to log in to the EC2 instance).

![Image](http://learn.nextwork.org/exuberant_orange_gentle_water_snake/uploads/aws-devops-vscode_2939cf01)

---

## Create the Application

### Exploring the project structure

Using VS Code's file explorer, I could see a bunch of folders and subfolders that defined the structure of the web application. The src (source) folder contains all the application’s source code, including the webapp directory (HTML, CSS, JavaScript, and JSP files) and the resources directory (configuration files such as database connection settings). The pom.xml file is the Maven Project Object Model file that stores the project configuration and dependency details used by Maven to build and manage the application.

Two of the project folders created by Maven are src and webapp, which define the main structure of the web application. The src (source) folder contains all the application’s source code and configuration files, while the webapp folder includes the core web application files such as HTML, CSS, JavaScript, and JSP that control how the application looks and functions.

![Image](http://learn.nextwork.org/exuberant_orange_gentle_water_snake/uploads/aws-devops-vscode_45f91fd7)

---

## Using Remote - SSH

### What I did in this step

In this step, I will connect VS Code directly to my EC2 instance. This is different from simply connecting to the EC2 instance through the terminal on my local machine, because that approach does not provide the full benefits of an IDE like VS Code.

By connecting VS Code itself to the EC2 instance, I can use powerful IDE features such as file navigation, code editing, and project management directly on the EC2 server, which makes development more efficient and convenient.

### Updating the web app

The index.jsp file is used in Java-based web applications and is similar to an HTML file because it contains markup to display web pages. However, unlike HTML, a JSP file can also include Java code, which allows it to generate dynamic content. This means the page content can change based on user input or data from a database. Social media applications are good examples of dynamic web apps because the content is constantly updated and personalized for each user. In contrast, HTML files are static and cannot run Java code. That is why installing Java on your Amazon Elastic Compute Cloud (EC2) instance is important, as it allows your web application to execute Java code properly.

I edited the index.jsp file by opening the index.jsp file under the src folder inside the webapp directory, pasted my content into it, and then pressed Ctrl + S to save the changes.

![Image](http://learn.nextwork.org/exuberant_orange_gentle_water_snake/uploads/aws-devops-vscode_7a1de541)

---

## Using nano

### Additional improvements

In this secret mission, I will edit the index.jsp file using the terminal instead of an IDE because it allows me to make quick changes directly on the server, which is useful when working on remote environments like an Amazon Elastic Compute Cloud (EC2) instance. It also helps improve my familiarity with Linux commands and file editing in real-world cloud and server environments.

### Terminal vs IDE

An alternative to using an IDE is editing files directly from the terminal. To do this, I navigated to the path of the index.jsp file using the cd command. In my case, the file location was `/home/ec2-user/nextwork-web-project/src/main/webapp`. After reaching the directory, I ran the command `nano index.jsp` to open the file. Nano is a terminal-based text editor where I added my content. Then I pressed Ctrl + O to save the changes and Ctrl + X to exit the editor.


Compared to using an IDE, editing index.jsp in the terminal felt simpler and faster for making quick changes directly on the server, but it was less convenient for features like syntax highlighting and navigation. I would be more likely to use an IDE when working on larger projects or when writing and debugging more complex code, as it provides better support and productivity features.

### Verifying my work

To verify my editing work in the terminal, I switched to the SSH remote window in VS Code and reopened the index.jsp file to confirm that my changes were saved successfully. It was possible to see my changes in VS Code right away because the file was being edited on the same remote server through the SSH connection, so any updates made from the terminal were immediately reflected there.

![Image](http://learn.nextwork.org/exuberant_orange_gentle_water_snake/uploads/aws-devops-vscode_a3324ad41)

---

---
