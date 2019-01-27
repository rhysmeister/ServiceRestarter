# ServiceRestarter
Randomly selects a node from the supplied cluster and restarts a service on that host


# Process overview

The included tasks file will perform the following operations...

1. Select random host from play_hosts.
2. Stop service.
3. Wait for interval.
4. Start service.
5. Wait for Service back up, Port?
6. Wait for second defined interval.

The outer playbook controls the execution of these tasks over multiple calls.

# Variables

service_name: The service to be restarted.
1st_interval: The 1st interval after the service has been stopped.
service_port: The service port that will be checked when the service is restarted.
wait_for_timeout: How long we will wait for the service port to start responding.
2nd_interval: The 2nd wait interval after the service has been restarted and the port responds.x
max_iterations: The maximum number of iterations.
port_delay: How long to wait before listening for the service port after a restart.
