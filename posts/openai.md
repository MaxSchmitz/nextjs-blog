---
title: 'OpenAI GPT-3'
date: '2022-02-20'
---

I’ve been using next.js a lot lately for my projects. It’s a really simple and elegant server-side JavaScript framework that makes it easy to get up and running with a project.

This time, I wanted to try deploying a next.js app that uses openAI to generate recipes. OpenAI has trained cutting-edge language models that are very good at understanding and generating text, and it’s already been used to create some amazing things, like this recipe generator.

The app is really simple. It uses the completions endpoint on the openai API. You input some text as a prompt, and the API will return a text completion that attempts to match whatever instructions or context you gave it. In this case I used some “Prompt engineering” to instruct the AI to write generic recipes.

You can try out the app yourself by cloning the repository on GitHub.

	git clone https://github.com/openai/openai-quickstart-node.git

Add your API key

	cd openai-quickstart-node
	cp .env.example .env

Run the app

	npm install
	npm run dev