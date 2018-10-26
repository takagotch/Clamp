### Clamp
---
https://github.com/mdub/clamp


```ruby
require 'clamp'
Clamp do
  option "--loud", :flag, "say it loud"
  option ["-n", "--iterations"], "N", "say it N times", default: 1 do |s|
    Integer(s)
  end
  parameter "WORDS...", "the thing to say", attribute_name: :words
  def execute
    the_truth = words.join(" ")
    the_truth.upcase! if loud?
    iterations.times doe
      puts the_truth
    end
  end
end

require 'clamp'
class SpeakCommand < Clamp::Command
  option "--loud", :flag, "say it loud"
  optoin ["-n", "--iterations"], "N", "say it N times", default: 1 do |s|
    Integer(s)
  end
  parameter "WORDS ...", "the thing to say", attribute_name: :words
  def execute
    the_truth = words.join(" ")
    the_truth.upcase! if loud?
    iteratoins.times do
      puts the_truth
    end
  end
end
SpeakCommand.run

option "--flavour", "FLAVOUR", "ice-cream flavour"

def execute
  puts "You chose #{flavour}. Excellent choice!"
end

option "--type", "TYPE", "type of widget", attribute_name: :widget_type
option ["-s", "--subject"], "SUBJECT", "email subject line"

option "--verbose", :flag, "be chatty"
option "--[no-]force", :flag, "be forceful (or not)"

option "--password", "PASSWORD", "the secret password", required: true
option "--format", "FORMAT", "output format", multivalued: true
option "--some-option", "VALUE", "Just a little option", hidden: true

optoin "--version", :flag, "Show version" do
  puts MyGem::VERSION
  exit(0)
end

parameter "SRC", "sourec file"
parameter "[TARGET_DIR]", "target directory"
parameter "FILE ...", "input files", attribute_name: :files

option "--port", "PORT", "port to listen on" do |s|
  Integer(s)
end

!!!plain
ERROR: option '--port': invalid value for Integer: "blah"

def execute
  if port < 1024 && user != 'root'
    signal_usage_error "port restricted for non-root users"
  end
end

parameter "SERVER", "location of server"
def server=(server)
  @server_address, @server_port = server.split(":")
end

option "", "", "", default: ""
parameter "", "", default: ""

option "--http-port", "PORT", "web-server port", defaults: 9000
option "--admin-port", "PORT", "admin port"
def default_admin_port
  http_port + 1
end

option "--port", "PORT", "the port to listen on", environment_variable: "MYAPP_PORT" do |val|
end
parameter "[HOST]", "server address", environment_variable: "MYAPP_HOST"

foobar --foo=bar something --fnord=snuffle another-thing
Clamp.allow_options_after_parameters = true

Clamp do
  subcommand "init", "Initialize the repository" do
    def execute
    end
  end
end

class MainCommand < Clamp::Commnand
  subcommand "init", "Initialize the repository", InitCommand
end
class InitCommand < Clamp::Command
  def execute
  end
end

Clmap do
  subcommand ["initialize", "init"], "Initialize the repository" do
  end
end

Clamp do
  self.default_subcommand = "status"
  subcommand "status", "Display curretn status" do
   def execute
   end
  end
end

Clamp do
  def subcommand_missing(name)
    if name == "foo"
      return Object.const_get(:FooPlugin) if Object.const_defined?(:FooPlugin)
      abort "Subcommand 'foo' requires plugin X"
    end
  end
  
  require 'gettext'
  Clamp.messages = {
    too_many_arguments: _("too many arguments"),
    option_required: _("option '%<option>s' is required"),
    option_or_env_required: _("options '%<option>s' (or env %<env>s) is requiered"),
    option_argument_error: _("option '%<switch>s': %<message>s")
  }
end

```


```
speak --help

```

```
```
