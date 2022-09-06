#!/bin/bash
#BSUB -P TRN001
#BSUB -W 00:05
#BSUB -nnodes 1
#BSUB -J cupy_timings
#BSUB -o cupy_timings.%J.out
#BSUB -e cupy_timings.%J.err
#BSUB -U TAPIA_THU

cd $LSB_OUTDIR
date

module load gcc/7.5.0
module load cuda/11.0.2
module load python

source activate $HOME/.conda/envs/cupy-summit
export CUPY_CACHE_DIR="${MEMBERWORK}/trn010/.cupy/kernel_cache"

jsrun -n1 -g1 python3 timings.py
