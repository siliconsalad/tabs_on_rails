require 'rake'
require 'rake/testtask'
require 'rake/rdoctask'

$:.unshift(File.dirname(__FILE__) + "/lib")
require 'lib/tabs_on_rails'

desc 'Default: run unit tests.'
task :default => :test

desc 'Test the tabs_on_rails plugin.'
Rake::TestTask.new(:test) do |t|
  t.libs << 'lib'
  t.libs << 'test'
  t.pattern = 'test/**/*_test.rb'
  t.verbose = true
end

desc 'Generate documentation for the tabs_on_rails plugin.'
Rake::RDocTask.new(:rdoc) do |rdoc|
  rdoc.rdoc_dir = 'rdoc'
  rdoc.title    = 'TabsOnRails'
  rdoc.options << '--line-numbers' << '--inline-source'
  rdoc.rdoc_files.include('README')
  rdoc.rdoc_files.include('lib/**/*.rb')
end

begin
  require 'jeweler'
  Jeweler::Tasks.new do |s|
    s.name        = TabsOnRails::GEM
    s.summary     = "Simple Rails plugin for creating and managing Tabs."
    s.email       = "weppos@weppos.net"
    s.homepage    = "http://github.com/weppos/tabs_on_rails"
    s.description = <<-EOD
      TabsOnRails is a simple Rails plugin for creating and managing Tabs. \
      It provides helpers for creating tabs with a flexible interface.
    EOD
    s.authors     = ["Simone Carletti"]
  end
rescue LoadError
  puts "Jeweler not available. Install it with: sudo gem install technicalpickles-jeweler -s http://gems.github.com"
end

begin
  require 'rcov/rcovtask'
  Rcov::RcovTask.new do |t|
    t.libs << 'test'
    t.test_files = FileList['test/**/*_test.rb']
    t.verbose = true
  end
rescue LoadError
  puts "RCov is not available. In order to run rcov, you must: sudo gem install rcov"
end

