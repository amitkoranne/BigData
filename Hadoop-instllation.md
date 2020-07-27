
1.  Download
https://hadoop.apache.org/release/2.7.2.html

2. ssh-keygen -t rsa
  cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys
  chmod og-wx ~/.ssh/authorized_keys 
  ssh localhost
  
3. core-site.xml 
<configuration>
	  <property>
		  <name>fs.defaultFS</name>
		  <value>hdfs://localhost:9000</value>
	  </property>
  </configuration>
  
4. # The java implementation to use.
export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk1.8.0_111.jdk/Contents/Home
export HADOOP_PREFIX=/Users/name/MyWorkspace/hadoop-install/hadoop-2.7.2
  
5. hdfs-site.xml
<configuration>
  <property>
    <name>dfs.replication</name>
    <value>1</value>
  </property>
</configuration>

6. yarn-site.xml

<configuration>

<!-- Site specific YARN configuration properties -->
   <property>
        <name>yarn.nodemanager.aux-services</name>
        <value>mapreduce_shuffle</value>
    </property>
</configuration>

7. Run
   bin/hadoop namenode -format
   sbin/start-dfs.sh
   http://localhost:50070/dfshealth.html#tab-overview
   

