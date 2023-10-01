<p align="center">
<img src="https://github.com/kennethmoen/Building-Intuition-For-DNS/assets/145589069/d6192fbb-d4fb-4f62-b6ed-806da21dc4ff"/>
</p>
<p 
In this lab will be inspecting DNS A-Records on the server, creating and deleting some of our own A-Records on the server (DC-1), inspecting them from Client-1 and exploring the importance of the flush dns command
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

<img src=""/>
<img src=""/>

</p>
<h2>Local DNS Cache Exercise</h2>
Go back to DC-1 and change mainframe’s record address to 8.8.8.8

<img src="https://github.com/kennethmoen/Building-Intuition-For-DNS/assets/145589069/e5d0c3ee-95c5-4804-9257-a8b1ea13efa6"/>

Go back to Client-1 and ping “mainframe” again. Observe that it still pings the old address. Even though we changed it on the DC server

<img src="https://github.com/kennethmoen/Building-Intuition-For-DNS/assets/145589069/9b3924f2-f4c3-4619-8440-178a38158521"/>

Observe the local dns cache (ipconfig /displaydns), flush the DNS cache (ipconfig /flushdns). Observe that the cache is empty

<img src="https://github.com/kennethmoen/Building-Intuition-For-DNS/assets/145589069/f2a44e48-7080-4b11-b444-9d2c1c22e3ed"/>

Attempt to ping “mainframe” again. Observe the address of the new record is showing up
<img src="https://github.com/kennethmoen/Building-Intuition-For-DNS/assets/145589069/2cdc6012-89b7-4eed-abe9-71a712fe1ad3"/>

"/>
</p>

</p>
<h2>CNAME Record Exercise</h2>

Go back to DC-1 and create a CNAME record that points the host “search” to “www.google.com”. This has no utility, it just shows you can map names to other names.

<img src="https://github.com/kennethmoen/Building-Intuition-For-DNS/assets/145589069/186d82c8-9429-4f90-9764-d4847c5f416c"/>

Go back to Client-1 and attempt to ping “search”, observe the results of the CNAME record

<img src="https://github.com/kennethmoen/Building-Intuition-For-DNS/assets/145589069/896af084-231d-423d-8b9c-914648dbaa33"/>

On Client-1, nslookup “search”, observe the results of the CNAME record

<img src="https://github.com/kennethmoen/Building-Intuition-For-DNS/assets/145589069/d24ab658-3659-48c5-931c-9510d0a513cd"/>
</p>
