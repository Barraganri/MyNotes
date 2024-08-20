## Create [[Google Cloud]] networks:
`gcloud compute networks create privatenet --subnet-mode=custom`
This creates a network called privatenet with custom subnet mode.

`gcloud compute networks subnets create privatesubnet-us --network=privatenet --region=US_Region --range=172.16.0.0/24`
Now it specifies region and range for the IPs

## Show network lists:
`gcloud compute networks list`

## Show available [[Virtual Private Network]]s
`gcloud compute networks subnets list --sort-by=NETWORK`






