# lesson terraform

## インストール
```bash
$ anyenv install --list
  tfenv
$ anyenv install tfenv
$ tfenv --version
tfenv 2.2.2-84-g459d15b

$ tfenv list-remote
$ tfenv install 1.0.10
$ tfenv list  
  1.0.10
$ tfenv use 1.0.10
Switching default version to v1.0.10
Switching completed

$ terraform --version
Terraform v1.0.10
on darwin_amd64
```

## 初期化
```bash
$ terraform init
```

## 構成の検証
```bash
$ terraform fmt
$ terraform validate
```

## 状態の適用
```bash
$ terraform apply
```

## 状態の検証
```bash
$ terraform show
```

## 状態の破棄
```bash
$ terraform destroy
```

## 変数の設定
```variables.tf
variable "instance_name" {
  description = "Value of the Name tag for the EC2 instance"
  type        = string
  default     = "ExampleAppServerInstance"
}
```
```main.tf
resource "aws_instance" "app_server" {
  ami           = "ami-08d70e59c07c61a3a"
  instance_type = "t2.micro"

  tags = {
    Name = var.instance_name
  }
}
```
