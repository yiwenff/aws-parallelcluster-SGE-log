# aws-parallelcluster-SGE-log
Auxiliary functions for running parallel jobs on AWS Parallelcluster using SGE

**1. Dead Nodes and Jobs**

**Problem identification**

When running SGE parallel jobs on AWS Parallelcluster using spot instances, instances get terminated/stopped and removed from host. However, instances stay as orphaned and corresponding jobs stay as fake running states.

**Current solution/suggestion from AWS Parallelcluster**

It's the users' responsibility to delete dead nodes and jobs.

**Description of the code**

This code automatically identifies the dead nodes and jobs attached to it. Dead jobs are forced deleted before removing dead nodes. The jobs attached to the live nodes will keep running.

Reference [Releted issues]:
https://github.com/aws/aws-parallelcluster/issues/1247
