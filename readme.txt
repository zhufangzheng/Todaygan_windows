测试：
cd C:\Users\12399\Desktop\GAN\project\Todaygan_me_windows
python test.py --phase test --serial_test --name robotcar_2day --dataroot C:\Users\12399\Desktop\GAN\project\datasets --n_domains 2 --which_epoch 150 --loadSize 512
下面我用预训练的模型对ToDayGAN model用更多图片进行了测试。运行test.py 文件，
--serial_test 表示按顺序从文件夹中读取每个图像一次，--name表示预训练模型的名字，dataroot表示测试集，n_domains_2表示两个域，
150个 epoch，并且把图片缩放到512像素再载入。
问题1：
RuntimeError: DataLoader worker (pid(s) 19764) exited unexpectedly
可能是线程的问题。
//将data_loader.py 文件中的numworkers = 1注释掉。