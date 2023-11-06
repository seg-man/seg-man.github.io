### **SOLO**

--config-file
configs/SOLOv2/R50_3x.yaml
--num-gpus
1
OUTPUT_DIR
training_dir/SOLOv2_R50_3x_DeBug

### **CondInst**

--config-file 

configs/CondInst/MS_R_50_1x.yaml 

--num-gpus

1 

OUTPUT_DIR 

training_dir/CondInst_MS_R_50_1x_debug

### SOLO eval

--config-file
configs/SOLOv2/R50_3x.yaml
--eval-only
--num-gpus
1
OUTPUT_DIR
training_dir/SOLO/SOLOv2_R50_3x_featbranch_addf0
MODEL.WEIGHTS
training_dir/SOLO/SOLOv2_R50_3x_featbranch_addf0/model_final.pth

## SparseInst

缺少的安装包 timm; shapely

```
--config-file
configs/sparse_inst_r50_base.yaml
--num-gpus
1
OUTPUT_DIR
train_dir/SparseInst_Debug
```

```
--config-file
configs/sparse_inst_r50_base.yaml
--num-gpus
1
--eval
MODEL.WEIGHTS
train_dir/SparseInst_Baseline/sparse_inst_r50_base_ff9809.pth
OUTPUT_DIR
train_dir/SparseInst_Debug
```

参数量，GFLOPs 计算：

```bash
python get_flops.py --num-inputs 100 --tasks flop --config-file ./configs/sparse_inst_r50_base.yaml MODEL.WEIGHTS ./train_dir/SparseInst/Encoder-Postprocess/model_final.pth
```

```bash
cd AdelaiDet-Raw/
python get_flops.py --num-inputs 100 --tasks flop --config-file ./configs/SOLOv2/Base-SOLOv2.yaml MODEL.WEIGHTS ./Model_Weights/SOLOv2_R50_3x.pth
python get_flops.py --num-inputs 100 --tasks flop --config-file ./configs/SOLOv2/R50_3x.yaml MODEL.WEIGHTS ./Model_Weights/SOLOv2_R50_3x.pth
python get_flops.py --num-inputs 100 --tasks flop --config-file ./configs/SOLOv2/Base-SOLOv2.yaml MODEL.WEIGHTS ./Model_Weights/SOLOv2_R50_3x.pth
```

## CRIS

```bash
--config config/refcoco/cris_r50.yaml --opts TRAIN.exp_name CRIS_Debug 
```





:snowflake:
