(a) Functional & Non-Functional Requirements – Passport Automation System
Functional Requirements

User Registration & Login

New user creates account

Authentication for login

Application Submission

Enter personal details, identity, address

Upload required documents

Appointment Scheduling

Choose available date & time at passport office

Payment Processing

Online payment for application fee

Verification Workflow

Police verification request

Status updates from respective authorities

Application Tracking

Real-time status view (submitted → verified → dispatched)

Passport Delivery

Integration with postal service to track delivery

Non-Functional Requirements

Performance

Fast response within 2–3 seconds

Security

Encrypt personal data, secure login, access control

Reliability

24/7 availability, minimal downtime

Usability

Simple UI for common users

Scalability

Handle high number of applicants

Maintainability

Easy to update modules

Backup & Recovery

Daily backup for data safety

--------------------------------

(b) Use Case Diagram – Passport Automation System

Actors
Applicant
Passport Officer
Police Department
Payment Gateway

Main Use Cases

Register/Login

Submit Application

Upload Documents

Pay Fees

Schedule Appointment

Police Verification

Check Status

Issue Passport / Reject

Dispatch Passport

🎯 Use Standard Representation

System boundary = “Passport Automation System”

Connect actors → use cases via associations

(You can draw using StarUML, Lucidchart, draw.io)




Applicant ----> Register, Login, Apply, Upload Docs, Track Status, Pay, Schedule Appointment
Admin ----> Approve / Reject, Manage Appointments
Police Dept ----> Verify Documents & submit report
Payment Gateway ----> Confirm Payment
----------------------------------------------------

🛠 Project Monitoring using Nagios (Complete Commands)
1️⃣ Install Nagios on Ubuntu
sudo apt update
sudo apt install nagios4 nagios-nrpe-plugin -y

2️⃣ Start and enable Nagios service
sudo systemctl start nagios
sudo systemctl enable nagios
sudo systemctl status nagios


Check status → Active (running) must show. Mention this in viva.

3️⃣ Access Web Monitoring Dashboard

Browser →

http://localhost/nagios


Login:

Username: nagiosadmin

Password: set during install

4️⃣ Check Monitoring Details

Inside web UI:

Hosts → Shows monitored machines

Click localhost

CPU Load

Disk Usage

Current Users

PING status

Services → HTTP, SSH, memory usage

Screenshots expected in exam: Host list + Service OK status.


----------------------------------
✅ TASK (d) Docker Task — Full Commands + Output

👉 Create a folder:

passport-project/
    Dockerfile
    index.html

STEP 1: Create index.html
<h1>Passport Automation System</h1>
<p>Docker Test Page</p>

STEP 2: Create Dockerfile
FROM nginx:latest
COPY ./index.html /usr/share/nginx/html/index.html
EXPOSE 80

STEP 3: Build Image
docker build -t passport-app:v1 .


Output:

Successfully built <container-id>
Successfully tagged passport-app:v1

STEP 4: Run Container
docker run -d -p 8080:80 passport-app:v1


Output:

<container-id>

STEP 5: Verify Container Running
docker ps


Output: container list with port 0.0.0.0:8080->80/tcp

STEP 6: Open in Browser
http://localhost:8080


Expected Output
Your HTML page appears ✔
📸 Screenshot this page



---------------------------------------------------------------------------

Nagios Monitioring

Step 4: Start Minikube
1.	Open a terminal (PowerShell or CMD). Do the following commands
2.	Start Minikube with a specified driver (e.g., Hyper-V, Docker, or VirtualBox). For example:
o	Hyper-V: 
o	minikube start --driver=hyperv
o	Docker: 
o	minikube start --driver=docker
3.	Verify Minikube is running:
4.	minikube status
________________________________________
Step 5: Interact with Minikube



Nagios Automation Steps
Step 1: Pull the Nagios Docker Image
•	Open a terminal and run:
docker pull jasonrivers/nagios:latest
Step 2: Run Nagios
•	Command:
docker run --name nagiosdemo -p 8888:80 jasonrivers/nagios:latest
Step 3: Access Nagios Dashboard
•	Open your browser and navigate to:
http://localhost:8888
o	Login Credentials:
	Username: nagiosadmin
	Password: nagios
o	Once logged in, explore:
	Hosts: View systems being monitored.
	Services: Check tasks being monitored (e.g., CPU usage).
	Alerts: Access recent notifications.
Step 4: Monitoring Host Details
1.	Navigate to the Host Information Page:
o	Select a host from the Hosts menu.
2.	Key Details:
o	Host Status: Indicates if the system is UP or DOWN.
o	Metrics: View CPU usage, memory status, and network activity.
o	Actions: Reschedule checks, disable notifications, or schedule downtime.
Step 5: Stop and Remove Nagios
1.	Stop the Container:
o	Command:
docker stop nagiosdemo
2.	Delete the Container:
o	Command:
docker rm nagiosdemo
3.	Remove the Image (Optional):
o	List images:
docker images
o	Delete the Nagios image:
docker rmijasonrivers/nagios:latest

4.	 Observe the docker containers in DockerHub, we can see the latest Nagios Installed running on port:8888



