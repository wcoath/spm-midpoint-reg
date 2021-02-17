# spm-midpoint-reg
Collection of scripts to run SPM pairwise longitudinal registration on the CS cluster

Insight 46 specific with (semi-)BIDS format images

1. The 'check_' python script checks which images can be submitted and makes a job list
2. The 'submit_' bash script submits the job list as an array to the cluster and sources 'setup_midpoint.sh' to set up the environment
3. The 'run_' python script sets up the job and runs SPM using the 'long_pairwise_job.m' script and then tidies the output
