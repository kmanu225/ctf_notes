# base
- namespace: limité les ressources avec qui on peut discuter, limite les
- cgroup: limite les allocations mémoires
- overlayfs: 

- container rootless: 
	- mesure de sécurité permettant de mapper les id des utiliateurs sur nobody par défaut permettant ainsi de limiter l'impacte d'une priviledge escalation qui aurait eu lieu dans un container.

- plusieurs possibilité de passer de docker à root