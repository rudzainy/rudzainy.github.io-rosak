---
layout: post
title: Current State of Malaysia
date: 2022-05-18 09:44 +0800
description:
image:
category: Life
tags: [ruby,gag]
published: true
sitemap: true
---

```
# state_of_malaysia.rb
# A simple Ruby program to illustrate current state of Malaysia

# This class represents a generalisation of leaders in Malaysia
class MalaysianLeaders
  def boleh_harap?
    return false
  end

  def are_not_fighting_for_power?
    return false
  end
end

# Currently, this loop will run forever...
loop do
 
  # Usually after elections or hostile takeovers
  country_leaders = MalaysianLeaders.new

  # TODO: Need to find a way to update return value of 
  # MalaysianLeaders.boleh_harap? to TRUE. Later lah...

  # This is hillariously true
  if country_leaders.boleh_harap?
    # TODO: Alamak, now need to find a way to update return value  
    # of MalaysianLeaders.are_not_fighting_for_power? to TRUE 
    # pulak dah. Later lah...

    if country_leaders.are_not_fighting_for_power?
      # The statement below is nice to read. However, until we
      # finish above TODOs, we'll never reach this part of the
      # code...
      puts "Malaysia Cemerlang, Gemilang, Terbilang 🇲🇾"
      break # Literally breaking us out of our misery
    end
  end

  puts "Rakyat struggles and still hoping for the best."
  
end
# This "end" word here marks the end of the program, not the end
# of the rakyat's struggles...
```