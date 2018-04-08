Vagrant.configure("2") do |config|

  config.vm.box = "dummy"
  config.vm.synced_folder ".", "/vagrant", disabled: true

  config.vm.provider 'aws' do |aws, override|
  # Please provide a working access_key_id  and secret_access_key
  aws.access_key_id = ' '
  aws.secret_access_key = ' '
  aws.keypair_name = 'assessment-dev'
  aws.instance_type = 't2.micro'
  aws.region = 'eu-west-1'
  aws.ami = 'ami-7d45150e'
  aws.security_groups = ['sg.assessment.dev.web']
  override.ssh.username = 'admin'
  override.ssh.private_key_path = '~/desktop/assessment-dev.pem'

  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provisioning/playbook.yml"
  end
end
