At work (a manufacturing company), the warehouse was often so full that we were shuffling product around, trying to make room for new production.  Whenever this happened, we would slow production down, and let the warehouse free up a little, and then often, become even more empty.  This was hard on the warehouse workers, cycling between too much work and too little.  It was hard on the production crew in the same way.  And yet, it was not clear what happy-medium production rate would keep the warehouse medium full and the production crew medium busy.

What I would do was, just set a reasonable production rate, and try to adjust it later, when it becomes clear that it was too high or too low.  This drove me a little crazy since when, for example, the warehouse got too full, it was clear we had to slow down production, but I had no idea by how much.  I would slow production down a little, and the warehouse would get even more full because I didn’t slow production enough.  At that point it would be urgent and I would have to stop production completely, as there was no room at all left.  That was a clear failure!

Choosing that right production rate was nearly hopeless too.  Even if someone could make a really good estimate of the ideal production rate, things would change.  For example, maybe the sales rate would change.  Yet, it often looked like the sales rate had changed, when really, it was only a number of orders getting pushed out with no impact on future sales.

So then we applied the method we’d already been successfully using to maintain the temperature on some production equipment, with the change that now we would use this method to maintain the inventory level instead of a temperature.  At the highest level, we can say this is a “closed loop” control system instead of an “open loop” system.  By closed loop, I mean that we have a control signal (the production rate) that we adjust automatically, depending on the output of the system (that is, depending on the warehouse utilization.)

More carefully, we used a PI control strategy.  The idea is straightforward.  There is an “error”, that is, the actual warehouse utilization minus the desired utilization.  The cumulative sum of the error over time, multiplied by some constant, plus the error itself, multiplied by some other constant, is used as the control signal, that is, as the target production rate.  That is our “closed loop”.

After implementing this strategy, and working for a while to find appropriate constants, we never had to manually set the production rate again.  At the same time, the warehouse maintained a very steady utilization, as did the production crew.

If you want to talk about how to choose the constants, please contact me.  If there is enough interest, I will write a post, and if not, at least we can talk about it.

Comments to: https://twitter.com/ArizonaJim4/status/1364779251099004931
