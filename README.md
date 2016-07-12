#### An Ambari Stack for HttpFS

To deploy, copy the entire directory into your Ambari stacks folder and restart Ambari:

```
cd /var/lib/ambari-server/resources/stacks/HDP/2.3/services/
git clone https://github.com/laurentedel/httpfs
sudo service ambari-server restart
```

Then you can click on 'Add Service' from the 'Actions' dropdown menu in the bottom left of the Ambari dashboard.

#### Remove HttpFS service
If you want to delete the HBase REST gateway service from the Ambari services list:

  - Stop the service via Ambari
  - Delete the service

```
curl -u $user:$pass -i -H 'X-Requested-By: ambari' -X DELETE http://$host:8080/api/v1/clusters/$cluster/services/HTTPFS
```

  - Remove artifacts 
  
```
rm -rf /var/lib/ambari-server/resources/stacks/HDP/2.3/services/httpfs
```
  - Restart Ambari
```
ambari-server restart
```
