+++
title = 'Ipad as Dev Machine'
date = 2025-01-10T00:52:24Z
draft = false
+++

I set up [coder](https://github.com/coder/coder) on my mac at home so that I can use my ipad as a remote dev machine.

The setup was actually very simple and required almost no tweaking for a minimal dockerized dev environment.

*The experience is surprisingly great which makes me want to get a 13 inch m4 ipad pro... having a function row with an esc key sounds amazing...*

### host (macbook at home)
```
# First, install Coder
curl -L https://coder.com/install.sh | sh

# Start the Coder server (caches data in ~/.cache/coder)
coder server

# Navigate to http://localhost:3000 to create your initial user,
# create a Docker template and provision a workspace
```

Coder even provides a public endpoint which makes everything so much easier. 
After booting up the workspace, you can access the public endpoint and access code-server which is a web based version of vs code.

Github codespaces is very similar but it takes ages to initially load the repository. And the fact that each codespace maps to one repository made things pretty annoying.
Coder gives me the flexibility to create repository specific workspaces and also one general workspace that I can use for multiple repositories.

Looking forward to tweaking/creating more workspaces that fit to my needs.