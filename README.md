<p align="center">
<img src="https://github.com/kennethmoen/Building-Intuition-For-DNS/assets/145589069/d6192fbb-d4fb-4f62-b6ed-806da21dc4ff"/>
</p>
<p 
In this lab will be inspecting DNS A-Records on the server, creating and deleting some of our own A-Records on the server (DC-1) and inspecting them from Client-1
</p>
<h1>A-Record Exercise</h1>
- Connect/log into DC-1 as your domain admin account (mydomain.com\jane_admin)
- Connect/log into Client-1 as an admin (mydomain\jane_admin)
- From Client-1 try to ping “mainframe” notice that it fails. Client-1 searched it's data base but couldn't find records of "mainframe" anywhere
<img src="https://github.com/kennethmoen/Building-Intuition-For-DNS/assets/145589069/1479ac8f-cf36-48ca-847d-d14e727fbdc1"/>

Will create a DNS A-record on DC-1 for “mainframe” and have it point to DC-1’s Private IP address

<img src="https://github.com/kennethmoen/Building-Intuition-For-DNS/assets/145589069/7e33f892-9774-4309-adb4-450836232014"/>

Go back to Client-1 and try to ping it. Observe that it works

<img src="https://github.com/kennethmoen/Building-Intuition-For-DNS/assets/145589069/ad5a5ec6-7c34-4c95-bec9-8a87d4fe18a1"/>
This is an arbitrary exercise, were just seeing what happens when you create an A-record so we can observe what happens on Client-1 when we do this




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
