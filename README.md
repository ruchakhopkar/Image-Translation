# Image-Translation
Pix2Pix

Please change the paths as required. I have used the official github repo which implemented Pix2Pix and CycleGAN and used it for my own application. This implementation helped me take a closer look at how the code is implemented.

Make sure both the A and B folders have same size images.
Both folders should have train, val, test
Paste the folder in /home/ruchak/image_translation/datasets
Run python combine_A_and_B.py --fold_A /home/ruchak/image_translation/datasets/sdbp1/cdsem 
--fold_B /home/ruchak/image_translation/datasets/sdbp1/cfib --fold_AB combine_sdbp
This will generate a combined dataset which can now be used for training

For training:
python train.py --dataroot ./datasets/combine_sdbp --name sdbp_pix2pix_cropped --model pix2pix --direction AtoB

For testing:
python test.py --dataroot ./datasets/combine_sdbp --name sdbp_pix2pix_cropped --model pix2pix --direction AtoB

For inference time:
python test.py --dataroot ./datasets/accuracy_test_cleaned --model pix2pix --phase test --name tdtem_blanked_complete --dataset_mode unaligned --direction AtoB --norm batch
