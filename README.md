# README

A minimal [Rails](https://rubyonrails.org) app for deploying to AWS with [Deployment.io](https://deployment.io). It has no database.

Deployment.io builds it with the `Dockerfile` that `rails new` generated. The image runs [Thruster](https://github.com/basecamp/thruster) in front of Puma, so the app listens on port 80, and `/up` is its health check.

The app reads its secret key from the `SECRET_KEY_BASE` environment variable (this repository has no `credentials.yml.enc`). Generate one with `openssl rand -hex 64` and add it to your Deployment.io environment's variables.
