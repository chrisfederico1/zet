## SSD Check and Alignment

* Use the following command to find out if you have an SSD
* Replace the (x) with your drive letter
-
`cat /sys/block/sd(x)/queue/rotational`
-
* Check alignment with the Parted tool
-
`parted /dev/sd(x)`
`align-check opt (n)`
-
* Replace x with drive letter and n with partition number
-
* Trim 
-
`sudo fstrim -v --all`

    #zettle #SSD #SSDCHECk #SSDAlign

