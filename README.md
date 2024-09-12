# Fitness Tracker
A MERN fitness tracker app.
https://capstone-fittness.onrender.com/

# Drive Demo Vedio 
https://drive.google.com/drive/folders/1T0zsUg4BphiRc3h3SF7YVTqxxtBRabw6?usp=sharing

## Description:

A user-friendly MERN-stack application that enables individuals to easily track and manage their daily fitness routines. Features include logging and tracking of both cardio and resistance exercises, viewing of workout history, and ability to delete exercises.

## Technology:

Project is created with:

- Mongoose
- Express.js
- React.js
- Node.js
- JWT Authentication

variable "environment" {
  description = "The environment in which to deploy resources."
  type        = string
  default     = "dev"
}

resource "aws_s3_bucket" "example" {
  count = var.environment == "dev" ? 1 : 0

  bucket = "my-example-bucket-${count.index}"
  acl    = "private"

  tags = {
    Name        = "my-example-bucket"
    Environment = var.environment
  }
}


terraform apply -var="environment=dev"


The count argument is used to conditionally create the S3 bucket. If var.environment is "dev", count will be 1, and the bucket will be created. Otherwise, count will be 0, and no bucket will be created.
count.index allows you to differentiate resources if you have multiple resources of the same type.







