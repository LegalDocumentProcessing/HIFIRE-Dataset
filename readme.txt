# HIFIR Dataset

HIFIR dataset is consists of Indian First Information reports (FIRs) collected from various police statios of India.
These documents are field in handwritinngs over printed form. HIFIR dataset is the first large scale multi-task dataset for Legal document analaysis and 
Recognition.

HIFIR dataset is divided in two parts : 1) HIFIR-Doc for tasks such as i) Text Object detection ii) Document VQA iii) Legal Reasoning VQA and 2) HIFIR-HWR for Handwriting recognition.

This repository has separate folders for each dataset and notebooks.



## HIFIR-Doc

All the annotations and ground truths are stored inside HIFIR-Doc's master.json file. Corresponding images for each annotations are also 
in "images" folder. We have followed 70-20-10 split for train,test and validation for model training and evaluationn.
Train-Test-Val split has been provided in train.json, test.json and val.json and images are in subsequent folders such as "train", "test" and "Val".

Master annotation file consists of 5 fields such as: images, categories, annotations, LRVQA-Q1 and LRVQA-Q2

Sample example of master.json: 

{
"images":[{
			"license": 0,
			"file_name": "Women PSWOMEN-0035-2017-1610__1.jpg",
			"coco_url": "n/a",
			"height": 1180,
			"width": 740,
			"date_captured": "",
			"flickr_url": "n/a",
			"darwin_url": "https://darwin.v7labs.com/api/v2/teams/cogito/uploads/498b52fd-e74d-4d41-8654-ac49c92c9fb3",
			"darwin_workview_url": "https://darwin.v7labs.com/workview?dataset=659034&item=01898796-a2d2-6f8f-7500-3dd6433124e5",
			"id": 98046577,
			"tag_ids": []
		}],
		
"categories": [{
			"id": 3270727197,
			"name": "Address",
			"supercategory": "root"
		},
		{
			"id": 3547446734,
			"name": "ActionTaken",
			"supercategory": "root"
		}],

"annotations": [{
			"id": 2,
			"image_id": 98046577,
			"category_id": 2635822410,
			"segmentation": [
				[
					204.48,
					56.82,
					254.79,
					59.01,
					251.19,
					73.93,
					228.98,
					74.91,
					204.48,
					75.99
				]
			],
			"area": 826.9815500000041,
			"bbox": [
				204.48,
				56.82,
				50.31,
				19.169999999999996
			],
			"iscrowd": 0,
			"extra": {
				"text": "BDN"
			}
		}],
"LRVQA-Q1": {
		"Women PSWOMEN-0035-2017-1610__1.jpg": {
			"ReceivedTime": "13.25 hrs",
			"OOODay": "From 28th April 17 to till date",
			"ReceivedDate": "On 07.12.17",
			"TimeDifferenceNotCalculated": false,
			"ReceivedDateTime": "2017-12-07T13:25:00",
			"OOODateTime": "2017-12-07T13:25:00",
			"TimeDifference": "0 days, 0 hours, 0 minutes",
			"question": "What is the difference in time between the occurrence of the event and when it was reported?"
		}
"LRVQA-Q2": {
		"Women PSWOMEN-0035-2017-1610__1.jpg": {
			"is-q2": false,
			"question": "Are the charges against accused bailable or not? If any of the charges are non-bailable answer 'Non-bailable' else 'Bailable'",
			"Answer": "-",
			"Sections": "478 (A)/325/313/406/34"
		}
}


"images" contain the list of the images and corresponding image "id". Each image has been assign an unique id.
"categories" also contain the list of annotated field names and "id" for each category.
"annotations" have the list of bounding boxes, category name and corresponding text for each annotated fields. One image consist of multiple annotations. Every annotation used "image_id" and 
"category_id" to identify corresponding images and categories. 

"LRVQA-Q1" and "LRVQA-Q2" are specifically used for Visual Question Answering on Legal Reasoning. For each image records contain the image name , question and its answers.



## HIFIR-HWR

HIFIR-HWR consists of "ocr_dataset.json" containing the ground truths for cropped handwritten lines/words images. The images are provided in "Images"  folder inside "HIFIR-HWR".