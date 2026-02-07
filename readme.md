To launch Claude Code, in claude-code-router, run
`uv run uvicorn server:app --host 0.0.0.0 --port 8082 --reload`
and in this repo, run
`setx ANTHROPIC_BASE_URL http://localhost:8082; claude`

Implementation steps:
* Test out with fixed video file according to youtube tutorial https://www.youtube.com/watch?v=qenAQwLvZfA
* Test that it works in browser
* Try OBS streaming to fixed location 
* Modify to serve streamed chunks from OBS fixed location
* Test that it works in browser
* Test serving through Cloudflare tunnel
* Test that stream is accessible through third device in browser over the internet
* Test that stream is accessible in vrchat
