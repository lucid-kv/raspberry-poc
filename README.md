# Lucid Proof-of-Concept - Raspberry Real Time Temperature

This Proof-of-Concept show how it's possible to store raspberry's temperature data into a lucid node and fetch it into a chart.

[Open the Demo →](https://lucid-kv.github.io/raspberry-poc/)

![](https://user-images.githubusercontent.com/5221349/80119611-36d2ff00-858a-11ea-8f63-1cba7c15648a.png)

# How to try it?

If you want to try it on your own Lucid node, it's easily possible!

## Create your own Lucid node

Firstly you need to deploy your own node on heroku:

<a href="https://heroku.com/deploy?template=https://github.com/lucid-kv/lucid" target="_blank">
  <img src="https://www.herokucdn.com/deploy/button.svg" height="32"/>
</a>

## Fork this repo

```bash
git clone https://github.com/lucid-kv/raspberry-poc
```

# I don't have any Raspberry

I can use the CPU temperature of any server or computer easily instead:

```bash
apt install lm_sensors
sensors -A | grep 'Core 0' | cut -d : -f 2 | xargs | cut -c2-5 | curl -X PUT --data-binary "$(</dev/stdin)" https://lucid-kv.herokuapp.com/api/kv/rasp_poc_temp
```
