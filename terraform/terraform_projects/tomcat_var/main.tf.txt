resource "aws_instance" "ec2terrafrom" {
  ami           = var.ami
  instance_type = var.instance_type
  key_name = "vinod_devops"
  user_data     = file("tomcat.sh")
  security_groups = ["vinod_demo_security"]
  count = 1
  tags ={
  Name = "my_terraform_htppd"
  }
}