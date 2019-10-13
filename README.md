# CHS
Notes on how to use CHS

### Running an EC2 instance

From AWSconsole, navigate to EC2/Instances

Highlight `SFM_Metashape`

`Actions/Instance state/Start` It will take a while...once the status checks are complete:

`Actions/Connect`

Two choices here: You can `Download Remote Desktop File` or `Get Password`

If you download a RDP file, you can click on it to run RDP.

If you choose `Get Password`, you will be prompted to provide a key that matches the Key Name that was associated with the EC2 instance when it was created. (You can change this, but it is complicated). Browse to the location where you have stored the secret key `.pem` file, and click. The text box will fill with gibberish...click on `Decrypt Password`, and you will get shorter gibberish that is the password used in RDP.

In either case, note the IP address for your instance, and copy the password into your clipboard.

Login using RDP. My computer suggests GS\Administrator as the username...but we are not in the GS domain, so you have to select other choices and enter `Administrator`. 

You might get a warning that the identity of the remote computer cannot be verified...click yes to ignore that.

Now you should be logged in and looking at a normal screen.

PS C:\data> aws s3 cp s3://cmgp-sfm/2019-09_OBX/images/jpg/2019_0913_ppk-photo-locations-mbase-GP113712.txt .
download: s3://cmgp-sfm/2019-09_OBX/images/jpg/2019_0913_ppk-photo-locations-mbase-GP113712.txt to .\2019_0913_ppk-photo
-locations-mbase-GP113712.txt

PS C:\data> aws s3 cp --recursive s3://cmgp-sfm/2019-09_OBX d:
