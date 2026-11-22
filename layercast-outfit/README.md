# Layercast outfit skill

A Claude skill that tells you what to wear today, layer by layer, from the hourly forecast for where you are and when you'll be out. It's the rules engine from the Layercast app, packaged as a skill.

## Install

Copy the `layercast-outfit` folder into your skills directory (for Claude Code, `~/.claude/skills/`), or upload it as a skill in Claude.

## First use

Ask "what should I wear today?". The skill asks a few quick questions (city or ZIP, Fahrenheit or Celsius, whether you run cold or warm, what you usually dress for, when you're out, kids, style notes) and saves your answers as a profile. Change anything later by just saying so.

Your profile is saved to Claude's memory if available, otherwise to `~/.layercast/profile.json`. It never goes in this repo.

## Daily routine

Schedule a daily prompt such as: "Use the layercast-outfit skill to post today's outfit." Scheduled runs use your saved profile and never ask questions.

## Weather data

[Open-Meteo](https://open-meteo.com/), CC BY 4.0. No API key needed. The free API is for non-commercial use only.

If Open-Meteo can't be reached (some sandboxed environments block it), the skill falls back to a WeatherBug or National Weather Service forecast page for your city or ZIP, then to search results. It checks that the page is for your place and today's date before using it. If a page has only the day's high, low, rain chance and wind, the skill estimates the hours you'll be out from those, and says so.

## License

MIT, see [LICENSE](../LICENSE).
