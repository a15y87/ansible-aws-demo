# ansible-aws-demo
ansible-aws-demo
# Setup environment
export ANSIBLE_VAULT_PASS=v3ryStr0nGpa55w0rd<br>
export AWS_ACCESS_KEY_ID="Access Key ID"<br>
export AWS_SECRET_ACCESS_KEY="Secret Access Key"<br>
# Provision VPC and EC2 instances
ansible-playbook provision.yml -i inventories/production/ --vault-password-file=./library/vault_pass -e "bastion_access_prefix=0.0.0.0/0"
# Deploy site
ansible-playbook site.yml -i inventories/production/ --vault-password-file=./library/vault_pass
