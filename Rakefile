# Rakefile added by John Mair (banisterfiend)

require 'rubygems/package_task'
require 'rake/clean'
require File.join(__FILE__, '../lib/chipmunk/version')

dlext = RbConfig::CONFIG['DLEXT']

CLEAN.include("ext/**/*.#{dlext}", 'ext/**/.log', 'ext/**/.o', 'ext/**/*~', 'ext/**/*#*', 'ext/**/.obj', 'ext/**/.def', 'ext/**/.pdb')
CLOBBER.include("**/*.#{dlext}", '**/*~', '**/*#*', '**/*.log', '**/*.o', 'doc/**')

def apply_spec_defaults(s)
  s.name = 'chipmunk'
  s.summary = 'ruby bindings for the chipmunk 5.1.0 physics engine'
  s.description = s.summary
  s.version = Chipmunk::VERSION
  s.author = 'Scott Lembcke, Beoran, John Mair (banisterfiend)'
  s.email = 'beoran@rubyforge.com'
  s.date = Time.now.strftime '%Y-%m-%d'
  s.require_path = 'lib'
  s.homepage = 'http://code.google.com/p/chipmunk-physics/'
end

# common tasks
task compile: :clean

spec = Gem::Specification.new do |s|
  apply_spec_defaults(s)
  s.platform = 'i386-mingw32'
  s.files = ['Rakefile',
             'README',
             'LICENSE',
             'lib/chipmunk.rb',
             'lib/chipmunk/version.rb']
end

# spec = Gem::Specification.new do |s|
#   apply_spec_defaults(s)
#   s.platform = Gem::Platform::RUBY
#   s.extensions = FileList["ext/**/extconf.rb"]
#   s.files = ["Rakefile",
#              "README",
#              "LICENSE",
#              "lib/chipmunk.rb",
#              "lib/chipmunk/version.rb"] +
#     FileList["ext/**/extconf.rb", "ext/**/*.h", "ext/**/*.c"].to_a
# end

Gem::PackageTask.new(spec) do |pkg|
  pkg.need_zip = false
  pkg.need_tar = false
end
