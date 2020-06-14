# CHROME DINO BUG

Just `copy and past` that in the console :
---
```JS

Runner.instance_.gameOver = ()=>{}
```
```JS
Runner.prototype.mahmedEnd = ()=>{
    Runner.instance_.playSound(Runner.instance_.soundFx.HIT);
    vibrate(200);

    Runner.instance_.stop();
    Runner.instance_.crashed = true;
    Runner.instance_.distanceMeter.acheivement = false;

    Runner.instance_.tRex.update(100, Trex.status.CRASHED);

    // Game over panel.
    if (!Runner.instance_.gameOverPanel) {
        Runner.instance_.gameOverPanel = new GameOverPanel(Runner.instance_.canvas,
            Runner.instance_.spriteDef.TEXT_SPRITE, Runner.instance_.spriteDef.RESTART,
            Runner.instance_.dimensions);
    } else {
        Runner.instance_.gameOverPanel.draw();
    }

    // Update the high score.
    if (Runner.instance_.distanceRan > Runner.instance_.highestScore) {
        Runner.instance_.highestScore = Math.ceil(Runner.instance_.distanceRan);
        Runner.instance_.distanceMeter.setHighScore(Runner.instance_.highestScore);
    }

    // Reset the time clock.
    Runner.instance_.time = getTimeStamp();
}
```

Then after you Score a HigherScore Just Call `Runner.instance_.mahmedEnd()` to save the Score :smile:.
---

