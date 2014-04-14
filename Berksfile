# source 'http://cookbooks.opscode.com/api/v1/cookbooks'
# source 'https://api.berkshelf.com'

def opsworks_cookbook(name)
  cookbook name, { :path => "./opsworks-cookbooks/#{name}" }
end

cookbook 'redis', github: 'coderanger/chef-redis', tag: '1.0.4'
cookbook 'glusterfs', github: 'alecpm/glusterfs-cookbook', tag: '0.1.1'

# We want to be explicit, since we don't explicitly include our
# packages, except when testing
cookbook 'varnish', '0.9.10'
cookbook 'gunicorn', '1.1.2'
cookbook 'supervisor', '0.4.10'
cookbook 'build-essential', '1.4.2'
cookbook 'apt', '2.3.8'
cookbook 'yum', '3.1.2'
cookbook 'yum-epel', '0.3.4'
cookbook 'git', '3.1.0'
cookbook 'sqlite', '1.0.0'
cookbook 'ulimit', '0.3.2'
cookbook 'nfs', '1.0.0'
cookbook 'line', '0.5.1'
cookbook 'python', '1.4.6'
cookbook 'runit', '1.5.10'

# For vagrant testing only
# group :testing do
# We include these to get their dependencies resolved
#   cookbook 'opsworks_deploy_python', path: './opsworks_deploy_python'
#   cookbook 'plone_buildout', path: './plone_buildout'
#   opsworks_cookbook 'dependencies'
#   opsworks_cookbook 'gem_support'
#   opsworks_cookbook 'scm_helper'
#   opsworks_cookbook 'ssh_users'
#   opsworks_cookbook 'haproxy'
#   opsworks_cookbook 'mod_php5_apache2'
#   opsworks_cookbook 'opsworks_agent_monit'
#   opsworks_cookbook 'opsworks_commons'
#   opsworks_cookbook 'opsworks_initial_setup'
#   opsworks_cookbook 'opsworks_java'
#   opsworks_cookbook 'opsworks_nodejs'
#   opsworks_cookbook 'deploy'
#   opsworks_cookbook 'ssh_host_keys'
#   opsworks_cookbook 'memcached'
#   opsworks_cookbook 'mysql'
#   opsworks_cookbook 'nginx'
#   opsworks_cookbook 'apache2'
#   # opsworks_cookbook 'opsworks_bundler'
#   # opsworks_cookbook 'opsworks_cleanup'
#   # opsworks_cookbook 'opsworks_custom_cookbooks'
#   # opsworks_cookbook 'opsworks_ganglia'
#   # opsworks_cookbook 'opsworks_rubygems'
#   # opsworks_cookbook 'opsworks_shutdown'
#   # opsworks_cookbook 'opsworks_stack_state_sync'
#   # opsworks_cookbook 'packages'
#   # opsworks_cookbook 'passenger_apache2'
#   # opsworks_cookbook 'php'
#   # opsworks_cookbook 'rails'
#   # opsworks_cookbook 'ruby'
#   # opsworks_cookbook 'unicorn'
#   # opsworks_cookbook 'agent_version'
#   # opsworks_cookbook 'ebs'
# end
