# **LAPORAN HASIL PRAKTIKUM SISTEM ADMINISTRASI SERVER MODUL 4**

1. Copy container lxc_php7.4 two times

   ```markdown
   sudo lxc-copy -n ubuntu_php7.4 -N ubuntu_php7.4_2 -sKD
   ```

   ```markdown
   sudo lxc-copy -n ubuntu_php7.4 -N ubuntu_php7.4_3 -sKD
   ```

   

   ![1](https://user-images.githubusercontent.com/92940432/148332036-9af31d9b-f778-4460-a9f5-0087b6137454.png)

   

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

   

   ![2](https://user-images.githubusercontent.com/92940432/148332043-1e54857e-9530-436f-936e-6eee0c312736.png)

   

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

   

   ![3](https://user-images.githubusercontent.com/92940432/148332045-617cc241-617b-4bcd-a5d2-2f9f21fb45eb.png)

   

4. Add lxc_php7_2.dev at hosts file

   ```markdown
   nano /etc/hosts
   ```

   

   ![4](https://user-images.githubusercontent.com/92940432/148332048-b5c70e6e-d573-4b12-a097-74e8a11cfdd8.png)

   

5. Change the server name in nginx

   ```markdown
   nano /etc/nginx/sites-available/lxc_php7.dev
   ```

   

   ![5](https://user-images.githubusercontent.com/92940432/148332050-f3e12f0a-295d-4482-92d0-f3da22bbca94.png)

   

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

   

   ![6](https://user-images.githubusercontent.com/92940432/148332051-b8c0b3c0-125a-44fd-90a4-25205a4d3d21.png)
   

7. Do the same steps for lxc_php7.4_3. Set ip with 10.0.3.120

   

   ![7](https://user-images.githubusercontent.com/92940432/148332053-bd893aab-8b0d-4bb2-8675-93f94e53f6d5.png)
   

8. Copy lxc debian_php5.6 two times.

   ```markdown
   root@sas02:~# sudo lxc-copy -n debian_php5.6 -N debian_php5.6_2 -sKD
   ```

   ```markdown
   root@sas02:~# sudo lxc-copy -n debian_php5.6 -N debian_php5.6_3 -sKD
   ```

   

   ![8](https://user-images.githubusercontent.com/92940432/148332054-d7d1020e-7851-4d0c-904d-cdb19b666d55.png)

   

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

   

   ![9](https://user-images.githubusercontent.com/92940432/148332056-7ed3d1f8-b6ec-4a23-b291-2505a11c8b83.png)

   

10. Go to debian_php5.6_2, set the ip address and apply.

    ```markdown
    nano /etc/network/interfaces
    ```

    ```markdown
    /etc/init.d/networking restart
    ```

    

    ![10](https://user-images.githubusercontent.com/92940432/148332059-6264d27e-6871-44fd-811f-fab8e595e7cc.png)

    

11. Add lxc_php5_2.dev in hosts file

    ```markdown
    nano /etc/hosts
    ```

    

    ![11](https://user-images.githubusercontent.com/92940432/148332061-d0e1dc8d-b97b-4534-86bd-b7090f1534f2.png)

    

12. Change the server name in nginx

    ```markdown
    nano /etc/nginx/sites-available/lxc_php5.dev
    ```

    

    ![12](https://user-images.githubusercontent.com/92940432/148332064-695d2cd2-c056-456e-9810-314d384741d5.png)

    

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

    

    ![13](https://user-images.githubusercontent.com/92940432/148332066-e6ecf1bb-e463-4fe6-bd7e-17969909779a.png)

    

14. Do the same steps for lxc_php5.6_3 and set ip address with 10.0.3.116

    

    ![14](https://user-images.githubusercontent.com/92940432/148332067-fd9977e8-81fc-4dcc-859c-fb8bf72d848f.png)

    

15. Registes every containers in /etc/hosts (vm), then do curl for each lxc.

    ````markdown
    nano /etc/hosts
    ````

    

    ![15](https://user-images.githubusercontent.com/92940432/148332069-37257413-4645-40f5-bffb-fe9b17713f55.png)

    

16. Run jmeter (before use load balancer), with number of threads (user) of 50, 100, and 150.

   * Number of Threads 50

    

   ![16 (a)](https://user-images.githubusercontent.com/92940432/148332341-104a8bab-1741-41e2-9a16-59564dc09b52.png)

    

   ![16 (b)](https://user-images.githubusercontent.com/92940432/148332347-28cd05b5-9f7b-4418-b986-cec5be48c60a.png)

    

   ![16 (c)](https://user-images.githubusercontent.com/92940432/148332348-e130cfae-e74c-466e-86ab-a91411038abb.png)

    

  ![16 (d)](https://user-images.githubusercontent.com/92940432/148332352-215a8a65-8503-4554-945a-3097cbf5ea2c.png)

    

  * Number of Threads 100

    

   ![16 (e)](https://user-images.githubusercontent.com/92940432/148332733-195fd614-6df1-431c-95b0-ecd20ab1f673.png)


   ![16 (f)](https://user-images.githubusercontent.com/92940432/148332359-6b4f11c7-95c7-4a64-a7bc-b8e1a83d5d08.png)
    

   ![16 (g)](https://user-images.githubusercontent.com/92940432/148332362-56d13829-dd7a-4928-a1f5-495b2d5ebade.png)

    

   ![16 (h)](https://user-images.githubusercontent.com/92940432/148332365-6adea89f-8415-4248-86be-b244badc361a.png)

    

   * Number of Threads 150

    

   ![16 (i)](https://user-images.githubusercontent.com/92940432/148332370-d8283c43-ada1-4ef9-971a-72c15089f8ef.png)
    

   ![16 (j)](https://user-images.githubusercontent.com/92940432/148332371-3078cd36-5a4c-41b7-a2ac-4357cfa3fc75.png)

    

   ![16 (k)](https://user-images.githubusercontent.com/92940432/148332374-28998bae-0545-4178-87c8-254241370d7d.png)

    

   ![16 (l)](https://user-images.githubusercontent.com/92940432/148332376-5e79d141-1854-47c2-935f-33da37c576c1.png)

    

17. Do configuration of load balancer for least_conn and ip hash in vm.local (vm)

    

    ![17](https://user-images.githubusercontent.com/92940432/148332843-c98ec77f-82ff-45fc-a9af-c3474d5a5fa3.png)
    

18. Run jmeter (after use load balancer), with number of threads (user) of 50, 100, and 150.

   * Number of Threads 50

    

   ![18 (a)](https://user-images.githubusercontent.com/92940432/148332855-81d1e66d-5113-4bc4-9f5a-db98f6ad58ec.png)
    

   ![18 (b)](https://user-images.githubusercontent.com/92940432/148332846-4aefd486-c5a1-4312-b8ff-e0484eb4622d.png)
    

   ![18 (c)](https://user-images.githubusercontent.com/92940432/148332913-15d59335-3ee2-4d52-857a-4ee8d499146c.png)

    

   ![18 (d)](https://user-images.githubusercontent.com/92940432/148332917-7a1c8749-8e4a-4ba0-a2ee-4ef24b739b13.png)

    

   * Number of Threads 100

    

   ![18 (e)](https://user-images.githubusercontent.com/92940432/148332918-7b4ae833-5775-4187-be24-4d2d565d0ede.png)

    

   ![18 (f)](https://user-images.githubusercontent.com/92940432/148332920-427bbfb1-f0fb-460e-8bb2-2afa86db34fd.png)

    

   ![18 (g)](https://user-images.githubusercontent.com/92940432/148332922-85e96c9e-6210-43eb-8fa1-cdacb8887f3b.png)

    

   ![18 (h)](https://user-images.githubusercontent.com/92940432/148332923-b4ffe304-630a-4be1-8e3f-422290d259f2.png)

    

   * Number of Threads 150

    

   ![18 (i)](https://user-images.githubusercontent.com/92940432/148332926-1f709396-4287-412a-ad00-db7a457f2f1a.png)

    

   ![18 (j)](https://user-images.githubusercontent.com/92940432/148332929-29ea2ff4-1564-4def-8352-e16187e6d850.png)

    

   ![18 (k)](https://user-images.githubusercontent.com/92940432/148332933-7d3bda8e-ed80-4c64-9b54-1d70f9a2f250.png)

    

   ![18 (l)](https://user-images.githubusercontent.com/92940432/148332934-03aa85b6-44a9-4bac-8fac-48bf682d5c40.png)




Analysis 

We take a sample from number of threads 50 users

* Without load balancer, the result for throuhgput is 36.3/sec (landing), 18.4/sec (blog), and 22.5/sec (app).
* When use load balancer, tresult for throuhput is 29.8/sec (landing), 18.1/sec (blog), and 19.3/sec (app).
  The conclusion is, when we use load balancer, the amount of users that accessing our web is faster or higher than without load balancer.

