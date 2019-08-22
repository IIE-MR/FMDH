# A pytorch implementation for paper "Fast and Multilevel Semantic-Preserving Discrete Hashing" BMVC-2019

## REQUIREMENTS
1. python >= 3.5.2
2. pytorch >= 0.4

## DATASETS
1. [MIRFLICKR-25K](http://press.liacs.nl/mirflickr/dlform.html)
2. MSCOCO: [train](http://images.cocodataset.org/zips/train2017.zip)
[val](http://images.cocodataset.org/zips/val2017.zip)

## USAGE
```python
usage: fmdh_mirflickr.py [-h] [--bits BITS] [--gpu GPU] [--arch ARCH]
                         [--max-iter MAX_ITER] [--epochs EPOCHS]
                         [--batch-size BATCH_SIZE] [--topk TOPK] [--m M]
                         [--m_wap M_WAP] [--C C] [--num-samples NUM_SAMPLES]
                         [--alpha ALPHA] [--beta BETA]
                         [--learning-rate LEARNING_RATE]

fmdh_mirflickr

optional arguments:
  -h, --help            show this help message and exit
  --bits BITS           binary code length (default: 16,32,64)
  --gpu GPU             selected gpu (default: 0)
  --arch ARCH           model name (default: resnet152)
  --max-iter MAX_ITER   maximum iteration (default: 20)
  --epochs EPOCHS       number of epochs (default: 1)
  --batch-size BATCH_SIZE
                        batch size (default: 64)
  --topk TOPK           top k (default: 100)
  --m M                 ndcg@m (default: 100)
  --m_wap M_WAP         ndcg@m (default: 100)
  --C C                 class number (default: 24)
  --num-samples NUM_SAMPLES
                        hyper-parameter: number of samples (default: 2000)
  --alpha ALPHA         hyper-parameter: alpha (default: 100000)
  --beta BETA           hyper-parameter: beta (default: 100)
  --learning-rate LEARNING_RATE
                        hyper-parameter: learning rate (default: 0.001)
```

## RESULT
### NDCG@100
<table>
    <tr>
        <td rowspan="2">Dataset</td>
        <td colspan="4">Code Length</td>
    </tr>
    <tr>
        <td >16 bits</td><td >32 bits</td> <td >64 bits</td>
    </tr>
    <tr>
        <td >MIRFLICKR-25K</td ><td >0.5517 </td> <td > 0.5793 </td><td > 0.6028</td>
    </tr>
    <tr>
        <td >MSCOCO</td ><td >0.5036  </td> <td >0.5370  </td><td > 0.5541</td>
    </tr>
</table>

### ACG@100
<table>
    <tr>
        <td rowspan="2">Dataset</td>
        <td colspan="4">Code Length</td>
    </tr>
    <tr>
        <td >16 bits</td><td >32 bits</td> <td >64 bits</td>
    </tr>
    <tr>
        <td >MIRFLICKR-25K</td ><td >2.501 </td> <td > 2.739 </td><td > 2.760</td>
    </tr>
    <tr>
        <td >MSCOCO</td ><td >1.501  </td> <td >1.618  </td><td > 1.633</td>
    </tr>
</table>

### Weighted MAP@100
<table>
    <tr>
        <td rowspan="2">Dataset</td>
        <td colspan="4">Code Length</td>
    </tr>
    <tr>
        <td >16 bits</td><td >32 bits</td> <td >64 bits</td>
    </tr>
    <tr>
        <td >MIRFLICKR-25K</td ><td >2.536 </td> <td > 2.723 </td><td > 2.722</td>
    </tr>
    <tr>
        <td >MSCOCO</td ><td >1.530  </td> <td >1.697 </td><td > 1.708</td>
    </tr>
</table>