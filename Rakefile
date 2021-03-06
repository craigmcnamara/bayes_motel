require 'rubygems'
require 'rake'
require 'lib/bayes_motel/version'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name = "bayes_motel"
    gem.summary = %Q{Bayesian classification engine}
    gem.description = %Q{http://www.mikeperham.com/2010/04/28/bayes_motel-bayesian-classification-for-ruby/}
    gem.email = "mperham@gmail.com"
    gem.homepage = "http://github.com/mperham/bayes_motel"
    gem.authors = ["Mike Perham"]
    gem.version = BayesMotel::VERSION
    gem.add_development_dependency "shoulda", ">= 0"
    # gem is a Gem::Specification... see http://www.rubygems.org/read/chapter/20 for additional settings
  end
  Jeweler::GemcutterTasks.new
rescue LoadError
  puts "Jeweler (or a dependency) not available. Install it with: gem install jeweler"
end

require 'rake/testtask'
Rake::TestTask.new(:test) do |test|
  test.libs << 'lib' << 'test'
  test.pattern = 'test/**/test_*.rb'
  test.verbose = true
end

begin
  require 'rcov/rcovtask'
  Rcov::RcovTask.new do |test|
    test.libs << 'test'
    test.pattern = 'test/**/test_*.rb'
    test.verbose = true
  end
rescue LoadError
  task :rcov do
    abort "RCov is not available. In order to run rcov, you must: sudo gem install spicycode-rcov"
  end
end

task :test => :check_dependencies

task :default => :test

require 'rake/rdoctask'
Rake::RDocTask.new do |rdoc|
  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "bayes_motel #{BayesMotel::VERSION}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
