#!/bin/bash
#BSUB -P TRN001
#BSUB -W 01:00
#BSUB -nnodes 1
#BSUB -J pytorch_cnn
#BSUB -o pytorch_cnn.%J.out
#BSUB -e pytorch_cnn.%J.err
#BSUB -alloc_flags smt4 gpumps
#BSUB -U TAPIA_THU

cd $LSB_OUTDIR
date

module load python
module load cuda

source activate /gpfs/alpine/world-shared/stf007/msandov1/public_envs/opence_clone
export MPLCONFIGDIR="${MEMBERWORK}/trn010/mpl_cache"

jsrun -n1 -a1 -c21 -g1 -b packed:21 -d packed python3 -u cnn.py
