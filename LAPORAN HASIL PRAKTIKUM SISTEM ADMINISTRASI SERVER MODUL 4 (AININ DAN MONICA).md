# **LAPORAN HASIL PRAKTIKUM SISTEM ADMINISTRASI SERVER MODUL 4**

1. Copy container lxc_php7.4 two times

   ```markdown
   sudo lxc-copy -n ubuntu_php7.4 -N ubuntu_php7.4_2 -sKD
   ```

   ```markdown
   sudo lxc-copy -n ubuntu_php7.4 -N ubuntu_php7.4_3 -sKD
   ```

   

   ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\1.png)

   

2. Run or start each containers.

   ```markdown
   lxc-start ubuntu_php7.4
   ```

   ```markdown
   lxc-start ubuntu_php7.4_2
   ```

   ```markdown
   lxc-start ubuntu_php7.4_3
   ```

   

   ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\2.png)

   

3. Go to ubuntu_php7.4_2, set the ip address and apply.

   ```markdown
   lxc-attach ubuntu_php7.4_2
   ```

   ```markdown
   nano /etc/netplan/10-lxc.yaml
   ```

   ```markdown
   netplan apply
   ```

   

   ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\3.png)

   

4. Add lxc_php7_2.dev at hosts file

   ```markdown
   nano /etc/hosts
   ```

   

   ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\4.png)

   

5. Change the server name in nginx

   ```markdown
   nano /etc/nginx/sites-available/lxc_php7.dev
   ```

   

   ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\5.png)

   

6. Check the configuration, do a restart and try to access it.

   ```markdown
   nginx -t
   ```

   ```markdown
   service nginx restart
   ```

   ```markdown
   curl -i http://lxc_php7_2.dev
   ```

   

   ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\6.png)

   

7. Do the same steps for lxc_php7.4_3. Set ip with 10.0.3.120

   

   ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\7.png)

   

8. Copy lxc debian_php5.6 two times.

   ```markdown
   root@sas02:~# sudo lxc-copy -n debian_php5.6 -N debian_php5.6_2 -sKD
   ```

   ```markdown
   root@sas02:~# sudo lxc-copy -n debian_php5.6 -N debian_php5.6_3 -sKD
   ```

   

   ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\8.png)

   

9. Run or start each containers.

   ```markdown
   lxc-start debian_php5.6
   ```

   ```markdown
   lxc-start debian_php5.6_2
   ```

   ```markdown
   lxc-start debian_php5.6_3
   ```

   

   ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\9.png)

   

10. Go to debian_php5.6_2, set the ip address and apply.

    ```markdown
    nano /etc/network/interfaces
    ```

    ```markdown
    /etc/init.d/networking restart
    ```

    

    ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\10.png)

    

11. Add lxc_php5_2.dev in hosts file

    ```markdown
    nano /etc/hosts
    ```

    

    ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\11.png)

    

12. Change the server name in nginx

    ```markdown
    nano /etc/nginx/sites-available/lxc_php5.dev
    ```

    

    ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\12.png)

    

13. Check the configuration, do a restart and try to access it.

    ```markdown
    nginx -t
    ```

    ```markdown
    service nginx restart
    ```

    ```markdown
    curl -i http://lxc_php5_2.dev
    ```

    

    ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\13.png)

    

14. Do the same steps for lxc_php5.6_3 and set ip address with 10.0.3.116

    

    ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\14.png)

    

15. Registes every containers in /etc/hosts (vm), then do curl for each lxc.

    ````markdown
    nano /etc/hosts
    ````

    

    ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\15.png)

    

16.  Run jmeter (before use load balancer), with number of threads (user) of 50, 100, and 150.

    [Number of Threads 50]

    

    ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\16 (a).png)

    

    ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\16 (b).png)

    

    ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\16 (c).png)

    

    ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\16 (d).png)

    

    [Number of Threads 100]

    

    ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\16 (e).png)

    

    ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\16 (f).png)

    

    ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\16 (g).png)

    

    ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\16 (h).png)

    

    [Number of Threads 150]

    

    ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\16 (i).png)

    

    ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\16 (j).png)

    

    ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\16 (k).png)

    

    ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\16 (l).png)

    

17. Do configuration of load balancer for least_conn and ip hash in vm.local (vm)

    

    ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\17.png)

    

18. Run jmeter (after use load balancer), with number of threads (user) of 50, 100, and 150.

    [Number of Threads 50]

    

    ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\18 (a).png)

    

    ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\18 (b).png)

    

    ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\18 (c).png)

    

    ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\18 (d).png)

    

    [Number of Threads 100]

    

    ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\18 (e).png)

    

    ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\18 (f).png)

    

    ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\18 (g).png)

    

    ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\18 (h).png)

    

    [Number of Threads 150]

    

    ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\18 (i).png)

    

    ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\18 (j).png)

    

    ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\18 (k).png)

    

    ![](C:\Users\TRIA YULITA\OneDrive\Dokumen\ITTS\SEMESTER 5\Sistem Administrasi Server\PRAK MODUL 4\18 (l).png)




Analysis 

We take a sample from number of threads 50 users

* Without load balancer, the result for throuhgput is 36.3/sec (landing), 18.4/sec (blog), and 22.5/sec (app).
* When use load balancer, tresult for throuhput is 29.8/sec (landing), 18.1/sec (blog), and 19.3/sec (app).
  The conclusion is, when we use load balancer, the amount of users that accessing our web is faster or higher than without load balancer.

