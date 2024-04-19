# aws-resize-image
#image resizing using aws lambda, s3 and sns

Automated Image Resizing and Transfer System Using AWS Services.
Key Features:
1.	Image processing automation: Automatically resize and optimize images upon upload.
2.	Secure storage: Store processed images in a secure and reliable S3 bucket.
3.	Real-time notifications: Receive immediate updates about image processing via SNS.
 

1.	Create a two bucket name real-image and resize-image.Don’t change other setting and save it.
2.	Create a Sns topic choose standard  and remain all setting same and save it and create a subscription add ARN of sns topic and in select protocol SNS and in endpoint create subscription.  And check the email and done confirmation .
3.	Create I am policy –createpolicy-select a s3  and  give tick to full access and in resources tick to -ALL == click to add perision for other choose SNS tick to full access and in resources tick ALL ==click add permission and lambda in read session tick on getlayerversion and in resoucres tick in ALL and click on next Give policy nameand then click create policy.  --------I am role choose in trusted entity type-aws service and in choose service lambda give s3,sns,lambda full access give role name  and click to create role.
4.	Create a lambda function(authorfromscratch) and give function name , in runtime choose python 3.9 and remain same all create function.
5.	Now go to lambda console and  in below configuration- and click permission- then click on rolename. In that console add permission right side icon and then attach policy in this search your policy name and add permission
6.	In lambda console add in trigger search s3 ,choose your source bucket because it triggered the lambda remain all same and last click acknowledge click on add
7.	Now below code in last there is layer option add layer because for resize the image we need python library called pillow Addlayer- specifyARn- 
	arn:aws:lambda:ap-south-1:770693421928:layer:Klayers-p39-pillow:1
               verify it  -click on Add.
8.	After done all the task ,now we can start test and go on my givehub account copy the python code and paste in  open lambda console below click on code paste the code. And then click on test  here create-new-event—give the event-name -private-template helloworld. Again test the code and deploy the code.
9.	Here some error is shown because we don’t put any object in bucket now go to s3 and now in bucket1 put the jpg image and upload it. And then you see automatically in bucket2 there is image come and size of that image is less than first image and at the same time in your email message is sent.
------------------------complete----------------------------------

