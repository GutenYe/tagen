require "rbconfig"
sudo = Process.pid != 0 && RbConfig::CONFIG["host_os"] !~ /mswin|mingw/ ? "sudo" : ""

desc "build a gem file"
task :release do
	run "gem build tagen.gemspec"
	run "gem push *.gem"
  run "#{sudo} gem install *.gem"
	run "rm *.gem"
end

desc "install a gem file"
task :install do
	run "gem build tagen.gemspec"
	run "#{sudo} gem install *.gem"
	run "rm *.gem"
end

desc "run guard"
task :test do
	run "bundle exec guard -c -n f"
end

desc "testing the libraray"
namespace :test do
	task :all do
		run "bundle exec rspec spec"
	end
end

desc "run yard server --reload"
task :doc do
	run "yard server --reload"
end

desc "clean up"
task :clean do
	run "rm *.gem"
end

def run cmd
	puts cmd
	system cmd
end
