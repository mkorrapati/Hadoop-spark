# Hadoop-spark

Setting up Hadoop cluster

Follow the instructions from http://www.novixys.com/blog/setup-apache-hadoop-cluster-aws-ec2/ until "Namenode: Password Less SSH" section of it. In the next section "Datanodes: Setup Public Key", we need to copy public key from <namenode> to <datanodes>. Instructions in that link are not clear for this part. Follow that step here(below) and continue to follow above link for rest of intructions.

"Datanodes: Setup Public Key"

Copy public key to authorized_keys file on namenode:

namenode> cat id_rsa.pub >> ~/.ssh/authorized_keys

On namenode, cat and copy to clipboard the public key:

namenode> cat ~/.ssh/id_rsa.pub
[select and copy to your clipboard]

ssh into each datanode, and append the contents of namenode's public key(from clipboard) into that datanode's authorized_keys file:

datanode1> cat >> ~/.ssh/authorized_keys

[paste your clipboard contents]

[ctrl+d to exit]

datanode2> cat >> ~/.ssh/authorized_keys

[paste your clipboard contents]

[ctrl+d to exit]

datanode3> cat >> ~/.ssh/authorized_keys

[paste your clipboard contents]

[ctrl+d to exit]
