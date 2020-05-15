---
layout: post
title:      "Creating a Caravan"
date:       2020-05-15 03:30:42 -0400
permalink:  creating_a_caravan
---


My rails project app is called Welcome To The Caravan. The goal was to simulate the game 'Final Fantasy Crystal Chronicles' in an extremely basic sense. 

My app is based on chance using the rand method which is perfect for a dice roll. 

As a user, you name a character, select their tribe and an adventure to attempt. In a way, having knowledge of the video game its based on will roughly improve your chances of success.

To keep things simple, I created four models, being User, Character, Battle and Adventure. 

The Battle model joins Characters and Adventures. It stores methods that calculate a given character success rate for chosen adventure. 

```
  def level_up
    if adventure.boss_lv >= character.lv
      new_lv = character.lv += 1
      character.update(lv: new_lv)
      'You leveled up!'
    else
      'This adventure is no match for you now! Choose another.'
    end
  end

  def game_over
    character.destroy
    'Game Over'
  end

  def dice_roll
    character.lv + rand(0..5)
  end

  def results
    if character.tribe == 'Clavat'
      dice_roll + bonus >= adventure.clavat_difficulty ? level_up : game_over
    elsif character.tribe == 'Lilty'
      dice_roll + bonus >= adventure.lilty_difficulty ? level_up : game_over
    elsif character.tribe == 'Selkie'
      dice_roll + bonus >= adventure.selkie_difficulty ? level_up : game_over
    else
      character.tribe == 'Yuke'
      dice_roll + bonus >= adventure.yuke_difficulty ? level_up : game_over
    end
  end
end
```


Creating these little algorithms were my favorite part of this project. 


In retrospect, I would have the tribe attribute become its own class for improved abstraction rather than create individualized methods.


