<p align="center">
  <img width="40%" height="40%" src="./assets/Carnations_logo_1000px.png">
</p>

<p align="center">
  <img width="60%" height="60%" src="./assets/Header-Title.png">
</p>

<h3 align="center">An Advanced Guide for running Mac OS X / macOS on Non-Apple Hardware.</h3>
<h4 align="center">Proudly presented to you by the Carnations Botánica & it's amazing contributors.</h4>

</br>
</br>
<h1 align="center">Need Help?</h1>
<p align="center">
  <img width="50%" height="50%" src="./assets/discord-logo-white.png">
</p>
<h4 align="center">If you run into any issues, you can join the <a href="https://discord.gg/eDptbT9NcV">The Botánica</a> Discord server! Feel free to ping the <span style="color: #ffe875;">@Dandelions (Helper)</span> role within a help channel for support.</h4>

</br>
</br>
<h1 align="center">Contributing to the Documentation</h1>
<p align="center">
  <img width="30%" height="30%" src="./assets/GitHub_Logo_White.png">
</p>
<h4 align="center">If you have any changes or improvements you'd like to contribute for review and merge, to update misinformation or outdated information, as well as maybe even adding whole new pages, you can follow the general outline below to get a local copy of the documentation running below.</h4>
<h6 align="center">Instructions written for macOS hosts but is adoptable to other OS's.</h6>

</br>

1. Install/Update ``brew`` 
   - Visit https://brew.sh/ for instructions and information.

2. Install/Update ``ruby``
   - Once ``brew`` is installed, you can run ``brew install ruby`` in your terminal.
   - If using ZSH (any recent versions of macOS) Be sure to read the post install text as it suggest you should run the following command to export to PATH:
      - ``echo 'export PATH="/usr/local/opt/ruby/bin:$PATH"' >> ~/.zshrc``
      - Restart Terminal for changes to apply.

3. Install/Update ``gem`` and ``bundler``
   - Run ``gem update`` in your terminal window.
   - Run ``gem install bundler`` in your terminal window.

4. Fork Core-Configuration-Docs, git clone your fork, navigate to your local directory.
   - ``git clone --recursive git@github.com:yourusername/Core-Configuration-Docs.git``
   - ``cd Core-Configuration-Docs/``

5. Installing Docs dependencies, and running the server.
   - Run ``bundle install`` in your terminal window.
   - Running ``bundle exec jekyll serve --incremental`` will build and run a live copy of the docs on port ``4000`` of ``127.0.0.1`` (localhost) by default.
      - ``bundle exec jekyll serve --host YOUR_IP_ADDRESS --port PORT --incremental``
      - If for whatever reason, when you CTRL+S a local file, and it does not automatically regenerate your live local preview, you can use the following to force polling and watching for changes. ``--watch --force-polling``

<h4 align="center">You'll now be able to see the changes you make update live so you can work quickly and preview the final look of your Markdown files easily. Once you are done making your changes you can then proceed to submit a Pull Request for review, and eventual merge to Main.</h4>
<h6 align="center">A big thanks to all contributors and future contributors! ꩓</h6>