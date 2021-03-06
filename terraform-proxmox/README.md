## Deployment with Terraform on Proxmox

1. Install a third-party plugin for Proxmox environment. Take it from [here](https://github.com/Telmate/terraform-provider-proxmox). Follow the [instructions](https://github.com/Telmate/terraform-provider-proxmox/blob/master/docs/installation.md).

2. Create special user for provisioning on Proxmox. It needs to have the following rights:
```
Datastore.AllocateSpace
Datastore.Audit
VM.Allocate
VM.Audit
VM.Clone
VM.Config.CDROM
VM.Config.CPU
VM.Config.Disk
VM.Config.HWType
VM.Config.Memory
VM.Config.Network
VM.Config.Options
VM.Migrate
VM.PowerMgmt
```

2. Create linux OS template with cloud-init on Proxmox;

3. Create your own file **terraform.tfvars** and put it into current folder. Example [here](terraform.tfvars.example);

4. Create your own file **public_keys** and put it into current folder, or use default from **~/.ssh/id_rsa.pub**. Example [here](public_keys.example);

5. Run the following commands:
```bash
terraform init
terraform validate
terraform plan
terraform apply
```
