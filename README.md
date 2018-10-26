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
  option "", :flag, ""
  optoin [], "", "", default: 1 do |s|
    Integer(s)
  end
  parameter "", "", attribute_name: :words
  def execute
    the_truth = words.join(" ")
    the_truth.upcase! if loud?
    iteratoins.times do
      puts the_truth
    end
  end
end
SpeakCommand.run




```


```
```

```
```
