

## 07/06/2017
Upgraded to 1.7.0.

It seems that there are something wrong with the kubeadm v1.7.0, new node can't
join in the cluster in "TLS bootstrap-auto approval" way. So I replace it with
kubeadm v1.6.6.
Because “group auto approver" had been dropped in v1.7, so there is a new strange
task in the `master` role, It will auto approve any csr every minutes(crontab).
when every node had joined into the cluster, the cronjob will be deleted and finish
the playbook.
