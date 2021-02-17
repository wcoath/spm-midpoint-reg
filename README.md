# spm-midpoint-reg

### A Collection of scripts to run SPM pairwise longitudinal registration on the CS cluster

Insight 46 specific with (semi-)BIDS format images, assumes niftis are zipped

1. The 'check_' python script checks which images can be submitted and makes a job list
2. The 'submit_' bash script submits the job list as an array to the cluster and sources 'setup_midpoint.sh' to set up the environment
3. The 'run_' python script sets up the job and runs SPM using the 'long_pairwise_job.m' script and then tidies the output

### example of header and one line of jobs list created by 'check_' script:

subject_label,baseline_session,followup_session,baseline_t1,followup_t1
10015124,10015124_01_PETMR_20151203,10015124_02_PETMR_20180606,/SAN/medic/insight46/analysis/gradwarp/sub-10015124/ses-baseline/anat/sub-10015124_ses-baseline_T1w_run-1_desc-gradwarp.nii.gz,/SAN/medic/insight46/analysis/gradwarp/sub-10015124/ses-followup/anat/sub-10015124_ses-followup_T1w_run-1_desc-gradwarp.nii.gz

### Example qsub command to submit jobs 1 to 10 of a job list:

qsub -t 1:10 submit_midpoint.sh job_list.csv

