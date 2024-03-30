<ol>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;tab-stops:list .5in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span dir="LTR"></span><strong>Creating a VPC (Virtual Private Cloud):</strong>
            <o:p></o:p>
        </span>
        <ul>
            <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;tab-stops:list .75in 1.0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;font-size:10.0pt;line-height:107%;"></span><span dir="LTR"></span>Go to the VPC Dashboard in the AWS Management Console.<o:p></o:p></span></li>
            <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;tab-stops:list .75in 1.0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;font-size:10.0pt;line-height:107%;"></span><span dir="LTR"></span>Click on "Your VPCs" in the left-hand navigation pane.<o:p></o:p></span></li>
            <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;tab-stops:list .75in 1.0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;font-size:10.0pt;line-height:107%;"></span><span dir="LTR"></span>Click on "Create VPC" and configure the VPC with the appropriate IPv4 block (e.g., 10.0.0.0/16) and create two subnets within this VPC (e.g., 10.0.0.0/24 for the public subnet and 10.0.1.0/24 for the private subnet).<o:p></o:p></span></li>
        </ul>
    </li>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;tab-stops:list .25in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span dir="LTR"></span>Setting Up Internet Gateway and Route Tables:<o:p></o:p></span></li>
</ol>
<ul>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>Create an internet gateway and attach it to your VPC to enable internet access for resources within the VPC.<o:p></o:p></span></li>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>Create route tables and associate them with the subnets. Ensure that the public subnet has a route to the internet gateway to allow outbound internet access for resources in that subnet.<o:p></o:p></span></li>
</ul>
<ol>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;tab-stops:list .25in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span dir="LTR"></span>Creating EC2 Instance:<o:p></o:p></span></li>
</ol>
<ul>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>Launch EC2 instances for your web server, database server, and NAT gateway in the appropriate subnets.<o:p></o:p></span></li>
</ul>
<ul>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>Go to the EC2 Dashboard and click "Launch Instance."<o:p></o:p></span></li>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>Choose the desired Amazon Machine Image (AMI) for your instances, and select the appropriate instance type and configuration.<o:p></o:p></span></li>
</ul>
<ol>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;tab-stops:list .25in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span dir="LTR"></span>Create a Security Group for the RDS DB Instance:<o:p></o:p></span></li>
</ol>
<ul>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>choose VPC.<o:p></o:p></span></li>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>In the left navigation pane, choose Security Groups.<o:p></o:p></span></li>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>Choose Create security group and then configure:<o:p></o:p></span></li>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>Security group name: DB Security Group<o:p></o:p></span></li>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>Description: Permit access from Web Security Group<o:p></o:p></span></li>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>VPC: Lab VPC<o:p></o:p></span></li>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>You will now add a rule to the security group to permit inbound database requests.<o:p></o:p></span></li>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>In the Inbound rules pane, choose Add rule<o:p></o:p></span></li>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>Configure the following settings:<o:p></o:p></span></li>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>Type: MySQL/Aurora (3306)<o:p></o:p></span></li>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>CIDR, IP, Security Group or Prefix List: Type sg and then select Web Security Group.<o:p></o:p></span></li>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>Choose Create security group<o:p></o:p></span></li>
</ul>
<ol>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;tab-stops:list .25in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span dir="LTR"></span>Create a DB Subnet Group<o:p></o:p></span></li>
</ol>
<ul>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>On the Services menu, choose RDS.<o:p></o:p></span></li>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>In the left navigation pane, choose Subnet groups.<o:p></o:p></span></li>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>Choose Create DB Subnet Group then configure:<o:p></o:p></span></li>
</ul>
<p style="line-height:107%;margin:0in 0in 0in .5in;text-indent:.5in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;">Name: DB-Subnet-Group<o:p></o:p></span></p>
<p style="line-height:107%;margin:0in 0in 0in .75in;text-indent:.25in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;">Description: DB Subnet Group<o:p></o:p></span></p>
<p style="line-height:107%;margin:0in 0in 0in 0.5in;text-indent:.5in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;">VPC: Lab VPC<o:p></o:p></span></p>
<ul>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>Scroll down to the Add Subnets section.<o:p></o:p></span></li>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>Expand the list of values under Availability Zones and<span>&nbsp; </span>select the first two zones: us-east-1a and us-east-1b.<o:p></o:p></span></li>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>Expand the list of values under Subnets and select the subnets associated with the CIDR ranges 10.0.1.0/24 and 10.0.3.0/24.<o:p></o:p></span></li>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>Choose Create<o:p></o:p></span></li>
</ul>
<ol>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;tab-stops:list .25in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span dir="LTR"></span>Create an Amazon RDS DB Instance<o:p></o:p></span></li>
</ol>
<ul>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>In the left navigation pane, choose Databases.<o:p></o:p></span></li>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>Choose Create database<o:p></o:p></span></li>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>Select MySQL under Engine Options.<o:p></o:p></span></li>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>Under Templates choose Dev/Test.<o:p></o:p></span></li>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>Under Availability and durability choose Multi-AZ DB instance.<o:p></o:p></span></li>
</ul>
<p style="line-height:107%;margin:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"></span></p>
<ul>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>Under Settings, configure:<o:p></o:p></span></li>
</ul>
<p style="line-height:107%;margin:0in 0in 0in .5in;text-indent:.5in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;">DB instance identifier: lab-db<o:p></o:p></span></p>
<p style="line-height:107%;margin:0in 0in 0in .5in;text-indent:.5in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;">Master username: main<o:p></o:p></span></p>
<p style="line-height:107%;margin:0in 0in 0in .5in;text-indent:.5in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;">Master password: lab-password<o:p></o:p></span></p>
<p style="line-height:107%;margin:0in 0in 0in .5in;text-indent:.5in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;">Confirm password: lab-password<o:p></o:p></span></p>
<ul>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>Under DB instance class, configure:<o:p></o:p></span></li>
</ul>
<p style="line-height:107%;margin:0in 0in 0in .5in;text-indent:.5in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;">Select<span>&nbsp; </span>Burstable classes (includes t classes).<o:p></o:p></span></p>
<p style="line-height:107%;margin:0in 0in 0in .5in;text-indent:.5in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;">Select db.t3.micro<o:p></o:p></span></p>
<ul>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>Under Storage, configure:<o:p></o:p></span></li>
</ul>
<p style="line-height:107%;margin:0in 0in 0in .5in;text-indent:.5in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;">Storage type: General Purpose (SSD)<o:p></o:p></span></p>
<p style="line-height:107%;margin:0in 0in 0in .5in;text-indent:.5in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;">Allocated storage: 20<o:p></o:p></span></p>
<ul>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>Under Connectivity, configure:<o:p></o:p></span></li>
</ul>
<p style="line-height:107%;margin:0in 0in 0in .5in;text-indent:.5in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;">Virtual Private Cloud (VPC): Lab VPC<o:p></o:p></span></p>
<ul>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>Under Existing VPC security groups, from the dropdown list:<o:p></o:p></span></li>
</ul>
<p style="line-height:107%;margin:0in 0in 0in .5in;text-indent:.5in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;">Choose DB Security Group.<o:p></o:p></span></p>
<p style="line-height:107%;margin:0in 0in 0in 1.0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;">Deselect default.<o:p></o:p></span></p>
<ul>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>Under Monitoring expand Additional configuration.<o:p></o:p></span></li>
</ul>
<p style="line-height:107%;margin:0in 0in 0in .5in;text-indent:.5in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;">Uncheck Enable Enhanced monitoring.<o:p></o:p></span></p>
<ul>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>Under Additional configuration, configure:<o:p></o:p></span></li>
</ul>
<p style="line-height:107%;margin:0in 0in 0in .5in;text-indent:.5in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;">Initial database name: lab<o:p></o:p></span></p>
<p style="line-height:107%;margin:0in 0in 0in 1.0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;">Uncheck Enable automatic backups.<o:p></o:p></span></p>
<p style="line-height:107%;margin:0in 0in 0in .5in;text-indent:.5in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;">Uncheck Enable encryption<o:p></o:p></span></p>
<ul>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>Choose Create database<o:p></o:p></span></li>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>Choose lab-db (choose the link itself).<o:p></o:p></span></li>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>Wait until Info changes to Modifying or Available.<o:p></o:p></span></li>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>Scroll down to the Connectivity &amp; security section and copy the Endpoint field.<o:p></o:p></span></li>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>Paste the Endpoint value into a text editor. You will use it later in the lab.<o:p></o:p></span></li>
</ul>
<ol>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;tab-stops:list .25in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span dir="LTR"></span>Interact with Your Database<o:p></o:p></span></li>
</ol>
<ul>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>To copy the WebServer IP address, choose on the Details drop down menu above these instructions, and then choose Show.<o:p></o:p></span></li>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>Open a new web browser tab, paste the WebServer IP address and press Enter.<o:p></o:p></span></li>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>Choose the RDS link at the top of the page.<o:p></o:p></span></li>
    <li style="line-height:107%;margin-bottom:0in;margin-right:0in;margin-top:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;"><span style="font-family:Symbol;"></span><span dir="LTR"></span>Configure the following settings:<o:p></o:p></span></li>
</ul>
<p style="line-height:107%;margin:0in 0in 0in .5in;text-indent:.5in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;">Endpoint: Paste the Endpoint you copied to a text editor earlier<o:p></o:p></span></p>
<p style="line-height:107%;margin:0in 0in 0in .5in;text-indent:.5in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;">Database: lab<o:p></o:p></span></p>
<p style="line-height:107%;margin:0in 0in 0in .5in;text-indent:.5in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;">Username: main<o:p></o:p></span></p>
<p style="line-height:107%;margin:0in 0in 0in .5in;text-indent:.5in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;">Password: lab-password<o:p></o:p></span></p>
<p style="line-height:107%;margin:0in 0in 0in .5in;text-indent:.5in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;">Choose Submit<o:p></o:p></span></p>
<p style="line-height:107%;margin:0in;"><span style="font-family:&quot;Times New Roman&quot;, serif;font-size:12pt;">The complete architecture you deployed is:<o:p></o:p></span></p>
<img src="lab-5-final-lab-architecture.png" alt="Diagarm">
