# AMC replication
# AMC has two repos, (1) the search implementation (2) pretrained/pruned network for evaluation

# Replicate Pruned network inference
# ----------------------------------
* Option1: use the search repo checkpoints/download.sh
* Download pruned network from [google drive](https://drive.google.com/drive/folders/1DuFhX_oVrodR2Ud839I82NfMFrwr8mjJ)

### Evaluate pruned model
```bash
python eval_mobilenet.py --model mobilenet_0.5flops --imagenet_path /data/dataset/imagenet/ilsvrc2012/torchvision/
```

### Search
```
python amc_search.py --job train --model mobilenet --dataset imagenet --preserve_ratio 0.5 --lbound 0.2 --rbound 1 --reward acc_reward --data_root /data/dataset/imagenet/ilsvrc2012/torchvision/ --ckpt_path ./checkpoints/mobilenet_imagenet.pth.tar --seed 2018
```
