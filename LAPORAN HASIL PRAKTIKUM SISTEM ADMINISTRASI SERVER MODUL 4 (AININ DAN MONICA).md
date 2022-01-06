# **LAPORAN HASIL PRAKTIKUM SISTEM ADMINISTRASI SERVER MODUL 4**

1. Copy container lxc_php7.4 two times

   ```markdown
   sudo lxc-copy -n ubuntu_php7.4 -N ubuntu_php7.4_2 -sKD
   ```

   ```markdown
   sudo lxc-copy -n ubuntu_php7.4 -N ubuntu_php7.4_3 -sKD
   ```

   

   ![1](https://user-images.githubusercontent.com/92940432/148330391-b5537743-5f55-4ac2-ba96-0bef9c1cb222.png)

   

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

   

   ![2](https://user-images.githubusercontent.com/92940432/148330399-4d9dcfa8-c8ff-47ef-8589-0da4dccf4cad.png)

   

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

   

   ![3](https://user-images.githubusercontent.com/92940432/148330549-e8b0230c-4885-4235-b367-020d04a5899b.png)

   

4. Add lxc_php7_2.dev at hosts file

   ```markdown
   nano /etc/hosts
   ```

   

   ![4](https://user-images.githubusercontent.com/92940432/148330406-87164279-3a85-4f1e-8b89-c49c5a677bc3.png)

   

5. Change the server name in nginx

   ```markdown
   nano /etc/nginx/sites-available/lxc_php7.dev
   ```

   

   ![5](https://user-images.githubusercontent.com/92940432/148330408-f511218b-457c-4f21-b373-5fb287453f4e.png)

   

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

   

   ![6](https://user-images.githubusercontent.com/92940432/148330411-90cb6e3b-b998-4c45-8035-41c3a4b84366.png)

   

7. Do the same steps for lxc_php7.4_3. Set ip with 10.0.3.120

   

   ![7](https://user-images.githubusercontent.com/92940432/148330412-7f850d42-8d7e-4364-8863-c32902e3ff01.png)

   

8. Copy lxc debian_php5.6 two times.

   ```markdown
   root@sas02:~# sudo lxc-copy -n debian_php5.6 -N debian_php5.6_2 -sKD
   ```

   ```markdown
   root@sas02:~# sudo lxc-copy -n debian_php5.6 -N debian_php5.6_3 -sKD
   ```

   

   ![8](https://user-images.githubusercontent.com/92940432/148330413-80d68973-a21b-45c9-b890-5e2be0305b2a.png)
   

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

   

   ![9](https://user-images.githubusercontent.com/92940432/148330416-211b96a3-244c-44a7-90b3-0be6bf0161e8.png)

   

10. Go to debian_php5.6_2, set the ip address and apply.

    ```markdown
    nano /etc/network/interfaces
    ```

    ```markdown
    /etc/init.d/networking restart
    ```

    

    ![10](https://user-images.githubusercontent.com/92940432/148330417-45b87713-4906-4e58-995b-3ca779722339.png)

    

11. Add lxc_php5_2.dev in hosts file

    ```markdown
    nano /etc/hosts
    ```

    

    [11](https://user-images.githubusercontent.com/92940432/148330420-9d72a224-fd77-4149-a904-5be608ecdecc.png)

    

12. Change the server name in nginx

    ```markdown
    nano /etc/nginx/sites-available/lxc_php5.dev
    ```

    

    ![12](https://user-images.githubusercontent.com/92940432/148330421-8e255d97-5d99-4908-8553-009a80823d53.png)

    

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

    

    ![13](https://user-images.githubusercontent.com/92940432/148330423-d47bb53f-5b4a-4067-a650-e95fc224bbaa.png)

    

14. Do the same steps for lxc_php5.6_3 and set ip address with 10.0.3.116

    

    ![14](https://user-images.githubusercontent.com/92940432/148330426-933d87ae-8338-49d6-84fe-22d3d34e4a50.png)

    

15. Registes every containers in /etc/hosts (vm), then do curl for each lxc.

    ````markdown
    nano /etc/hosts
    ````

    

    ![15](https://user-images.githubusercontent.com/92940432/148330427-4e048137-644f-4cd5-8371-4daae1036923.png)

    

16.  Run jmeter (before use load balancer), with number of threads (user) of 50, 100, and 150.

      Number of Threads 50

    

    ![16 (a)](https://user-images.githubusercontent.com/92940432/148331208-9530b932-6499-4530-8d02-dc0fe9676aaa.png)


    

    ![16 (b)](https://user-images.githubusercontent.com/92940432/148331218-4133364a-cbd3-4f22-903f-5e8b7bd13b19.png)

    

    ![16 (c)](https://user-images.githubusercontent.com/92940432/148331224-80979e55-e4b9-4559-b820-b5aa2e6843dd.png)
    

    ![16 (d)](https://user-images.githubusercontent.com/92940432/148331226-66962e11-9333-42b4-8716-bb516b404689.png)

    

    [Number of Threads 100]

    

    ![16 (e)](https://user-images.githubusercontent.com/92940432/148331227-cafc499c-2b78-4f94-a71a-0f5e7375e922.png)

    

    ![16 (f)](https://user-images.githubusercontent.com/92940432/148331229-a99ba1f8-925a-4df9-993d-0690de303d1e.png)

    

    ![16 (g)](https://user-images.githubusercontent.com/92940432/148331230-a9372ce9-d222-440a-9e6d-7c5065adca47.png)

    

    ![16 (h)](https://user-images.githubusercontent.com/92940432/148331232-319c5512-827b-49b2-86b2-c25b3950224b.png)
    

    [Number of Threads 150]

    

    ![16 (i)](https://user-images.githubusercontent.com/92940432/148331233-963e5c5f-f68e-47e2-ac4a-ced4a3c2f074.png)
    

    ![16 (j)](https://user-images.githubusercontent.com/92940432/148331235-437cca5f-638a-4518-aa8d-803325456023.png)

    

    ![16 (k)](https://user-images.githubusercontent.com/92940432/148331237-f254109b-21e7-4798-8e5e-5c0e72c8c327.png)

    

    [16 (l)](https://user-images.githubusercontent.com/92940432/148331241-3a1a64d2-e527-4eb4-8328-648df6bc1d6c.png)

    

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

