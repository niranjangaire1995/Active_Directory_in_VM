# Active_Directory_in_VM
Active Directory in VM

I set up an active directory in my pc. I downloaded the windows server 2022 which will be used as a domain controller. I didnt have windows license, so i continued without the license and it allowed me to keep the server for 60 days and I also downloaded the windows 11 to be used a user for the AD. Windows 11 took forever to install, so i downloaded .iso file of windows 10 instead.

I have taken screenshots of every steps from the installation to setting a wallpaper with Group Policy Management Feature. This is a small demonstration to keep track for myself incase I forget this in the future. There are some steps where I was stuck, I will mention those as well. 

<img width="1919" height="1010" alt="Screenshot 2025-11-12 215805" src="https://github.com/user-attachments/assets/ad2df361-6a67-46a5-a8b4-69b5d3ca90e1" />
Image: Windows 10 installation for client

Note: Proceed with Un-attended installation is required if you dont want to sit and wait for the VM to be installed.
<img width="1919" height="1013" alt="Screenshot 2025-11-12 215818" src="https://github.com/user-attachments/assets/7aae64c4-8117-4837-b187-2256286bd442" />

The Un Attended installation will ask too many questions like inputting product key. It also gives and option to install < Emphasize guest edition here> guest edition. This allows the full screen view after the OS is installed in VM. 

I chose the memory and space. It depends on the size of ram and hard drive space in the host machine. More ram means more faster and smooth os in the vm.
<img width="1919" height="1020" alt="Screenshot 2025-11-12 215836" src="https://github.com/user-attachments/assets/133ad93e-76f6-45c4-9a20-882beaebeb14" />

<img width="1919" height="991" alt="Screenshot 2025-11-12 215915" src="https://github.com/user-attachments/assets/7dbcb7e8-3033-456f-85c0-5561a392e990" />
Image: windows Server VM installation for Active Directory Domain Server
<img width="1179" height="961" alt="Screenshot 2025-11-12 220100" src="https://github.com/user-attachments/assets/5420313f-f590-43fa-9948-c857327f874f" />
<img width="1146" height="927" alt="Screenshot 2025-11-12 220113" src="https://github.com/user-attachments/assets/fe9aa9a8-c1dc-4943-8790-0e59878e4097" />
<img width="1919" height="1022" alt="Screenshot 2025-11-12 220209" src="https://github.com/user-attachments/assets/14948a73-bf8e-49ba-a177-9f94d08d5e0f" />
<img width="1919" height="1021" alt="Screenshot 2025-11-12 220250" src="https://github.com/user-attachments/assets/dedeebc0-39fa-4d9f-a08e-50d40ff8f377" />
<img width="1907" height="1023" alt="Screenshot 2025-11-12 220416" src="https://github.com/user-attachments/assets/3d76b16e-8ea7-4d47-85f1-67cdb5d90009" />
Image: Used Windows 10 pro because other editions like Windows 10 Home doesnt allow us to add the windows in the Active Directory
<img width="1919" height="1015" alt="Screenshot 2025-11-12 220455" src="https://github.com/user-attachments/assets/52657610-adac-4acd-9cdd-9e82e6e8e76b" />

<img width="1919" height="1025" alt="Screenshot 2025-11-12 222328" src="https://github.com/user-attachments/assets/68e6f515-2e99-48d0-a934-d185bc103dd3" />

<img width="979" height="929" alt="Screenshot 2025-11-12 222409" src="https://github.com/user-attachments/assets/a7e14059-efe7-4bd2-90f9-a9c1591c002f" />
Image: Doesnt allow us to press control + alt + delete as this will invoke the host machine not the vm, so I used, the input and keyboard button and went to insert ctrl + alt + del instead

<img width="1919" height="1017" alt="Screenshot 2025-11-12 225735" src="https://github.com/user-attachments/assets/4dd7ea86-f967-48e3-85e1-862aa5cd6ef8" />

Image: Client Vm on the left and Server vm on the right showing the Server Manager application running


I had to shut down both vms after they were done installing. I had to set up the NAT Network so both vm could communicate while having access to internet as provided by my host machine.




<img width="563" height="434" alt="Screenshot 2025-11-12 234223" src="https://github.com/user-attachments/assets/099f651d-6cd5-4166-b6f8-232e96780622" />
Image: clicking tools and then to Network to set up NAT Network


<img width="1919" height="1022" alt="Screenshot 2025-11-12 234908" src="https://github.com/user-attachments/assets/676b0d06-34cc-4e57-b320-183c59e651af" />
Image: Click on NAT Network as shown in the Figure and click create and at the bottom, we could set up the Name and IPV4 Prefix. THe DHCP checkmark should be left unchecked. This is because, we are using the DHCP server in the Active Directory Server vm to distribute the ip addresses. Having DHCP checked causes the Virtual Box to provide Ip to the vms running in the Oracle Virtual Machine.

<img width="969" height="638" alt="Screenshot 2025-11-13 002359" src="https://github.com/user-attachments/assets/ec9e19b4-42be-4516-9942-2977785a87f0" />
Image: Now we go to the setting of both VM's and then to Expert and select Network and in the adapter setting, we select the NAT Network we created. 
NOte: NAT and NAT network are two different things.

The vms are on now and I wanted to insert the guest edition cd as I didnt do the unattended installation on this step. 
I go to Devices -> Insert Guest Additions CD Image  -> we see the CD drive of the windows installation inside the vm we are running.


<img width="1919" height="1021" alt="Screenshot 2025-11-13 003317" src="https://github.com/user-attachments/assets/70192b29-76de-45d3-8190-33f61ba77ca4" />

we now click the vboxwindowsadditions file and let it install.
<img width="1919" height="1019" alt="Screenshot 2025-11-13 003352" src="https://github.com/user-attachments/assets/464a2318-4e80-429a-ba66-b4019984aba1" />
<img width="1919" height="1024" alt="Screenshot 2025-11-13 003414" src="https://github.com/user-attachments/assets/4f24a375-e562-4bc3-978d-2dc176497829" />

<img width="1919" height="1026" alt="Screenshot 2025-11-13 003443" src="https://github.com/user-attachments/assets/47559d88-ab11-4b68-8ce1-96262550ebec" />

In the server manager app, we click, Add roles and Features button.
<img width="1919" height="1023" alt="Screenshot 2025-11-13 003533" src="https://github.com/user-attachments/assets/51f1137d-7d63-4195-8319-ba4c8edf02f7" />
After clicking the add roles and features button, we see this:

<img width="1919" height="1021" alt="Screenshot 2025-11-13 003551" src="https://github.com/user-attachments/assets/f3235317-3f8a-43ef-90e8-72060c661350" />

Next -> Role Based or Feature based Installation




<img width="1917" height="1020" alt="Screenshot 2025-11-13 003614" src="https://github.com/user-attachments/assets/b910fd8e-3df3-4d7a-854e-fd1a140f6655" />

select a server from the server pool -> next 
<img width="1919" height="1025" alt="Screenshot 2025-11-13 003834" src="https://github.com/user-attachments/assets/5d66e59f-caf5-4503-9f21-48e861cd6650" />

select = DHCP Server | DNS Server | File and storage services -> web server(iis) -> next 
<img width="1917" height="1021" alt="Screenshot 2025-11-13 003932" src="https://github.com/user-attachments/assets/55ed3bb1-2344-4673-9ef5-32614d9ff78d" />

Next -> Next -> Next (We will see validatin results and no static ip error -> we will add this later. 
<img width="1034" height="787" alt="Screenshot 2025-11-13 004152" src="https://github.com/user-attachments/assets/7787e281-3463-4b6c-ac77-6aea704604d1" />
<img width="1036" height="759" alt="Screenshot 2025-11-13 010154" src="https://github.com/user-attachments/assets/f9b2f072-2e36-4d70-ba09-e9555163d719" />

After installation is running in the background, we can see this. This will take a few minutes. 

Click this server to a domain controller as seen in the picture below:

<img width="1018" height="767" alt="Screenshot 2025-11-13 011141" src="https://github.com/user-attachments/assets/eabb3a78-3c4d-45f4-b69b-7e37c21ed495" />

Click add a new forest -> Root Domain Name: homelab.local
The format could be anything such as domainname.tld      -> the name of the domain and the top level domain(TLD)
<img width="1028" height="765" alt="Screenshot 2025-11-13 011334" src="https://github.com/user-attachments/assets/2c800268-13d6-4fdb-9e38-92f97f9c33a4" />

Set the password and click next

<img width="1023" height="772" alt="Screenshot 2025-11-13 011414" src="https://github.com/user-attachments/assets/70271bfe-50a1-4443-856e-960ebb2d12e3" />

The NetBIOS domain name : mine was homelab.
<img width="1019" height="768" alt="Screenshot 2025-11-13 011508" src="https://github.com/user-attachments/assets/dbd551ad-95fa-4c5d-b6a3-51652a66b579" />

Next -> Next -> Next
<img width="1028" height="770" alt="Screenshot 2025-11-13 011529" src="https://github.com/user-attachments/assets/56ab6769-3799-42d9-b4e3-f6e646443dfd" />
<img width="1024" height="763" alt="Screenshot 2025-11-13 011549" src="https://github.com/user-attachments/assets/34a4296b-e7e9-415d-bf83-1d1404ecb209" />

Click Install ->
<img width="1022" height="759" alt="Screenshot 2025-11-13 011604" src="https://github.com/user-attachments/assets/e948380a-19c0-45c7-b13f-f2d903cad1b1" />

It will restart the system:
<img width="1027" height="774" alt="Screenshot 2025-11-13 011700" src="https://github.com/user-attachments/assets/83bed873-b51a-4f0e-8843-ca6cb9032ff4" />

We will see the Administrator login page upon login, the password is what we set up earlier.
<img width="1023" height="768" alt="Screenshot 2025-11-13 012132" src="https://github.com/user-attachments/assets/6833e380-322c-4fce-8666-f17dcc8b3c55" />



The Network Setting of the VM should be set up like this. The Default Gateway(10.0.2.1/24) is the closest to the Network ID i.e 10.0.2.0/24.
The DNS is the server IP that the client will use. 
Alterate DNS is set up as google DNS.

<img width="494" height="560" alt="Screenshot 2025-11-13 004631" src="https://github.com/user-attachments/assets/3c057356-ad46-48df-a99b-cc00c79c8f08" />

Upon opening the Server Manager page we see the flag with yellow exclamation that says complete DHCP Config. This is where we set up dhcp so that client gets ip from this server.

<img width="1029" height="771" alt="Screenshot 2025-11-13 012237" src="https://github.com/user-attachments/assets/f8c73b72-b28b-4dfd-a9b3-d3ebdb421645" />

Click use the following user credential for DHCP server: UserName is what we used earlier i.e HOMELAB\Adminstrator -> Click commit button

<img width="765" height="560" alt="Screenshot 2025-11-13 012332" src="https://github.com/user-attachments/assets/b8417a68-4156-4920-94f7-b7e537d92e13" />


Tools -> DHCP

<img width="1020" height="767" alt="Screenshot 2025-11-13 012426" src="https://github.com/user-attachments/assets/d3f5a3c3-f9d1-4987-be94-5d803ba2232c" />

we see this window:
<img width="946" height="695" alt="Screenshot 2025-11-13 012505" src="https://github.com/user-attachments/assets/c8a01274-d1f8-47f3-9101-af5ec47fb970" />

Right click the IPV4 -> New Scope:
<img width="1022" height="762" alt="Screenshot 2025-11-13 012521" src="https://github.com/user-attachments/assets/3bcd7818-5a52-4c71-a84c-4a352d158036" />



Since we know the Net ID, and the first one is the default gateway i.e 10.0.2.1, we put the 10.0.2.2 as the start ip and end ip is 10.0.2.253 since 10.0.2.254 is the server's own address. 
while .255 is the broadcast address.The length /24  is the subnet.
<img width="1031" height="762" alt="Screenshot 2025-11-13 013007" src="https://github.com/user-attachments/assets/266f63f2-86f2-4209-b02b-2ab46b6f0155" />


The lease period for the IP is set up here:
<img width="953" height="692" alt="Screenshot 2025-11-13 013045" src="https://github.com/user-attachments/assets/b9d685e2-a812-467f-91c7-fc6ba6c23380" />


This step is asking for the Default Gateway for the client:
<img width="947" height="699" alt="Screenshot 2025-11-13 013130" src="https://github.com/user-attachments/assets/97719c09-69cd-4081-8f1a-3e099d6cae4c" />

Next step is again about the parent domain i.e, homelab.local that was set up earlier.
we add the server Ip here:
<img width="1025" height="762" alt="Screenshot 2025-11-13 013151" src="https://github.com/user-attachments/assets/31d66586-db2e-4673-83f4-ee247c868ce9" />

After clicking Next -> the scope is added now -> we can see it in the scope -? address leases
<img width="1009" height="729" alt="Screenshot 2025-11-13 013645" src="https://github.com/user-attachments/assets/3bd5ae93-5d6d-4403-81fa-247dea150f4e" />



The client machine can ping the server vm ip address:
<img width="1033" height="863" alt="Screenshot 2025-11-13 014040" src="https://github.com/user-attachments/assets/f76d7c29-7d3b-4b3f-a48a-c30f8a8192b4" />


Now i went to the advanced system settings and I clicked the change domain and added the domain i.e homelab.local 
It couldnt join the domain.
The reason number 1 was because I forgot the uncheck the dhcp in the NAT setting of the vm and I didnt assign the DNS of the client as the server dns.

<img width="1011" height="762" alt="Screenshot 2025-11-13 014644" src="https://github.com/user-attachments/assets/48d9da17-0415-47a5-9f24-13b70e01fb0c" />


After fixing two bugs, I was prompted for Admin username and password to join the domain.
<img width="1011" height="834" alt="Screenshot 2025-11-13 014747" src="https://github.com/user-attachments/assets/83993063-645a-461d-94d1-1085872c05d2" />




<img width="1027" height="800" alt="Screenshot 2025-11-13 014851" src="https://github.com/user-attachments/assets/2b706292-9994-42e3-ba3a-b7c4b5a5c2fd" />


























