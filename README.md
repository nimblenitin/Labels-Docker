# Labels-Docker

Steps to-
 
- Apply labels to swarm nodes
- Inspect the node labels
- Filter swarm nodes by labels

```

1. Use the following command to list all the nodes in the swarm cluster:
$ sudo docker node ls

2. Use the following command to add a label to a swarm node:
$ sudo docker node update --label-add workerNode hostname
Note: Replace hostname with IP address of Worker1 node

3. Use the following command to add multiple labels to a swarm node:
$ sudo docker node update --label-add workerNode --label-add worker1 hostname
Note: Replace hostname with IP address of Worker1 node

4. Use the following command to add a type label to identify nodes:
$ sudo docker node update --label-add type=queue hostname
Note: Replace hostname with IP address of Worker1 node

5. Use the following command to inspect a node for Labels:
$ sudo docker node inspect hostname
Note: Replace hostname with IP address of Worker1 node

6. Use the following command to inspect a node with a specific output format to get the node’s labels:
$ sudo docker node inspect --format ‘{{ .Spec.Labels }}’ hostname
Note: Replace hostname with IP address of Worker1 node

7. Use the following command to filter swarm nodes based on Labels:
$ sudo docker node ls -q | xargs sudo docker node inspect -f '{{ .ID }} \
[{{ .Description.Hostname }}]: {{ .Spec.Labels }}'


```
