# UAN
Code for Universal Adversarial Networks

![Alt text](figs/overview.png?raw=true "")

In this paper, we use generative models to compute universal adversarial perturbations. The generator is not conditioned on the images and so creates a perturbation that can be applied to any image to create an adversarial example.

We get pretty pictures like this:

![Alt text](figs/uap_example.png?raw=true "")

Clean Image              +          Perturbarbation          ==         Adversarial Image  

-------

Target model training steps:

For ImageNet

  - Clone https://github.com/Cadene/pretrained-models.pytorch into this directoy and (for easy python importing) rename to "pretrained_models_pytorch"

For CIFAR-10

  - Train some models using https://github.com/kuangliu/pytorch-cifar
  
  
-------

To run the attack, choose between ImageNet and CIFAR-10 and specify the model.

e.g. "python main.py --cuda --epochs 200 --batchSize 25 --shrink 0.00075 --shrink_inc 0.0001 --l2reg 0.00001 --restrict_to_correct_preds 1 --netClassifier resnet152 --imageSize 224 --outf resnet-results --every 100"


Note: For best results on ImageNet, batch size needs to be large. This takes up a lot of memory.
