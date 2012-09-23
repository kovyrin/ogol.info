load 'deploy'

# Capistrano configuration
server 'hosting.kovyrin.net', :app, :web, :db, :primary => true

set :application, 'ogol.info'
set :repository,  'git@github.com:kovyrin/ogol.info.git'
set :deploy_to, '/home/hosting/sanyok/ogol.info'

# Deploy params
set :scm, 'git'
set :branch, ENV['BRANCH'] || 'master'
set :deploy_via, :remote_cache
set :scm_verbose, true

# User info
set :use_sudo, false
set :user, 'sanyok'

# Capistrano tasks
namespace :deploy do
  desc 'Tasks to execute after code update'
  task :after_update_code, :roles => :app do
    run "chown sanyok:hosting #{release_path} -R"
  end

  desc 'No finalization needed'
  task :finalize_update do
  end

  desc 'No restarting needed'
  task :restart do
  end
end
