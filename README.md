<h2>Tutorial: Ruby on Rails - Learn Web Development with Rails</h2>
<h3>&nbsp;&nbsp;&nbsp;&nbsp;Michael Hartl<br />
&nbsp;&nbsp;&nbsp;&nbsp;<code>http://ruby.railstutorial.org/ruby-on-rails-tutorial-book</code><br />
&nbsp;&nbsp;&nbsp;&nbsp;=> <code>https://github.com/criedo/RoRTutorial_HartlM</code></h3>
<br />
<b>ruby -v</b> => ruby 1.9.3p327 (2012-11-10 revision 37606) [x86_64-linux]<br />
<b>gem -v</b> => 1.8.24<br />
<b>rails -v</b> => Rails 3.2.9<br />
<br />
<b>ruby_path</b>: ./home/criedo/.rvm/rubies/ruby-1.9.3-p327/bin<br />
<b>project_path</b>: [cd ~/projects/RoRTutorial_HartlM]<br />
<code>cd ~/projects</code><br />
<code>sudo mkdir RoRTutorial_HartlM</code><br />
<code>sudo chmod a=rx RoRTutorial_HartlM</code><br />
<code>sudo chmod u+w RoRTutorial_HartlM</code><br />
<code>cd RoRTutorial_HartlM</code><br />
<code>sudo gedit README.markdown</code><br />
<code>sudo chmod a=rw README.markdown</code><br />
<h3>Chapter 1 From zero to deploy</h3>
<ul>
<li><b>download</b>: 'The Well Grounded Rubyist - Black, David A. (2009)'<br />
&nbsp;&nbsp;&nbsp;&nbsp;from http://ebookbrowse.com/gdoc.php?id=364567597&url=b710df116262f74a213890c609318019<br />
&nbsp;&nbsp;&nbsp;&nbsp;=> C:\Download\prog\ruby\tutorial\The Well Grounded Rubyist - Black - Manning (2009).pdf</li>
<li><b>links</b>:<br />
http://railsforzombies.org/<br />
http://tryruby.org/levels/1/challenges/0<br />
http://railscasts.com/<br />
http://guides.rubyonrails.org/<br />
[scaling] http://idleprocess.wordpress.com/2009/11/24/presentation-summary-high-performance-at-massive-scale-lessons-learned-at-facebook/<br />
[ide] RadRails => http://www.aptana.com/products/radrails<br />
[ide] RubyMine => http://www.jetbrains.com/ruby/buy/index.jsp [Commercial License: €142; Personal License: €66; Open Source Project License: Free]<br />
[ide] 3rd Rail => http://www.embarcadero.com/products/3rdrail [RAD Studio: €5,115.81]<br />
[editor] Sublime Text 2 => http://www.sublimetext.com/2 [US$59] [https://github.com/mhartl/rails_tutorial_sublime_text]<br />
[editor] vim => http://www.vim.org/<br />
[js] http://nodejs.org/</li>
<li><b>installing RVM - Rails</b>: <i>convenient to create separate gemsets, which are self-contained bundles of gems</i><br />
<code>rvm use 1.9.3@rails3tutor --create --default</code><br />
<code>which gem</code> =&gt; /home/criedo/.rvm/rubies/ruby-1.9.3-p327/bin/gem<br />
<code>sudo gedit ~/.gemrc</code><br />
<i>&nbsp;&nbsp;&nbsp;&nbsp;install: --no-rdoc --no-ri<br />
&nbsp;&nbsp;&nbsp;&nbsp;update: --no-rdoc --no-ri</i><br />
<code>gem install rails -v 3.2.9</code><br />
<code>rails -v</code> =&gt; <b>Rails 3.2.9</b><br />
<code>sudo apt-get install libxslt-dev libxml2-dev libsqlite3-dev</code> =&gt; 0 upgraded, 0 newly installed, 0 to remove and 0 not upgraded.<br />
<code>rails new first_app</code> =&gt; Your bundle is complete! Use `bundle show [gemname]` to see where a bundled gem is installed.<br />
<code>cd first_app/</code><br />
<code>sudo gedit Gemfile</code><br />
<i>source 'https://rubygems.org'<br />
<br />
gem 'rails', '3.2.9'<br />
<br />
group :development do<br />
&nbsp;&nbsp;&nbsp;&nbsp;gem 'sqlite3', '1.3.5' [previous: 1.3.6]<br />
end<br />
<br />
# Gems used only for assets and not required in production environments by default.<br />
group :assets do<br />
&nbsp;&nbsp;&nbsp;&nbsp;gem 'sass-rails',   '3.2.5'<br />
&nbsp;&nbsp;&nbsp;&nbsp;gem 'coffee-rails', '3.2.2'<br />
<br />
&nbsp;&nbsp;&nbsp;&nbsp;gem 'uglifier', '1.2.3' [previous: 1.3.0]<br />
end<br />
<br />
gem 'jquery-rails', '2.0.2' [previous: 2.1.4]</i><br />
<code>bundle install</code><br />
<code>rails server</code> => <i>ERROR</i>: Could not find a JavaScript runtime<br />
<code>sudo apt-get install nodejs</code><br />
<code>rails server</code> =&gt; [2012-12-02 14:54:49] INFO  WEBrick[ 1.3.1]::HTTPServer#start: pid=6239 port=3000</code><br />
<p><b>into the browser</b>: <code>http://localhost:3000/</code></p></li>
<li><b>installing Git</b><br />
<code>git config --global user.name "criedo"</code><br />
<code>git config --global user.email cfriedo@yahoo.com</code><br />
<code>git config --global alias.co checkout</code><br />
<code>git config --global core.editor "sudo gedit"</code><br />
<code>git config --list</code> => <i>user.name ...</i><br />
<code>git init</code> =&gt; Initialized empty Git repository in /home/criedo/projects/RoRTutorial_HartlM/.git/<br />
<code>sudo gedit .gitignore</code><br />
<i># See http://help.github.com/ignore-files/ for more about ignoring files.<br />
#<br />
# Ignore bundler config<br />
/.bundle<br />
<br />
# Ignore the default SQLite database.<br />
/db/*.sqlite3<br />
<br />
# Ignore all logfiles and tempfiles.<br />
/log/*.log<br />
/tmp<br />
<br />
# Ignore other unneeded files.<br />
doc/<br />
*.swp<br />
*~</i><br />
<code>git add .</code><br />
<code>git status</code> =&gt; # On branch master [...]<br />
<code>git commit -m "Initial commit"</code> =&gt; [master (root-commit) 8aa5dcf] Initial commit - 38 files changed, 1265 insertions(+) [...]<br />
&nbsp;&nbsp;&nbsp;&nbsp;<b>important to note that Git commits are local</b><br />
<code>git log</code> =&gt; commit 8aa5dcfd8135afe0d94d6d2b06447a148451e477 [...]<br />
&nbsp;&nbsp;&nbsp;&nbsp;undo the changes by having Git check out the previous commit with the checkout command (-f flag to force overwriting the current changes)</code><br />
<p><b>Generating SSH Keys</b> [https://help.github.com/articles/generating-ssh-keys#]</p>
<code>ssh-keygen -t rsa -C "cfriedo@yahoo.com"</code><br />
=&gt; Enter file in which to save the key (/home/criedo/.ssh/id_rsa): [Enter]<br />
&nbsp;&nbsp;&nbsp;Enter passphrase (empty for no passphrase):crfr97 [Enter]<br />
&nbsp;&nbsp;&nbsp;Enter same passphrase again:crfr97 [Enter]<br />
&nbsp;&nbsp;&nbsp;=&gt; The key fingerprint is: 04:d9:79:bc:9e:f8:dc:bf:2a:e6:d6:77:2c:52:ad:77 cfriedo@yahoo.com<br />
<code>sudo apt-get install xclip</code><br />
<code>xclip -sel clip &lt ~/.ssh/id_rsa.pub</code>
<p><b>into the browser</b>: <code>https://github.com/</code><br />
<ul><li>Enter and go to Account Settings</li>
<li>Click "SSH Keys" in the left sidebar</li>
<li>Click "Add SSH key"</li>
<li>Paste your key into the "Key" field</li>
<li>Click "Add key"</li>
<li>Confirm the action by entering your GitHub password<br />
<code>ssh -T git@github.com</code> =&gt; The authenticity of host 'github.com (207.97.227.239)' can't be established.<br />
&nbsp;&nbsp;&nbsp;# RSA key fingerprint is 16:27:ac:a5:76:28:2d:36:63:1b:56:4d:eb:df:a6:48.<br />
&nbsp;&nbsp;&nbsp;# Are you sure you want to continue connecting (yes/no)?</i><code>yes [Enter]</code><br />
&nbsp;&nbsp;&nbsp;Hi criedo! You've successfully authenticated, but GitHub does not provide shell access.</li></ul>
<p><b>sending code to github.com</b></p>
<code>git remote add origin git@github.com:criedo/RoRTutorial_HartlM.git</code><br />
<code>git push -u origin master</code><br />
&nbsp;&nbsp;&nbsp;&nbsp;=&gt; <i>ERROR</i>: github [rejected] master -> master (non-fast-forward) error [https://help.github.com/articles/dealing-with-non-fast-forward-errors]<br />
<code>git push -u origin master --force</code> =&gt; Writing objects: 100% (64/64), 27.15 KiB, done.<br /></li>
<li><b>Branch, edit, commit, merge</b><br />
<i>branches</i> are effectively copies of a repository where we can make changes without modifying the parent files - the full value of branching becomes clear when working on a project with multiple developers<br />
<ul><li>to create a new topic branch (checkout with the -b flag):<br />
<code>git checkout -b <i>name</i></code></li>
<li>to lists all the local branches (the asterisk * identifies which the currently branch)<br />
<code>git branch</code></li>
<li>after creating the topic branch, edit it to make it a little more descriptive:<br />
to rename a file in the git:<br />
<code>git mv <i>old_name</> <i>new_name</i></code><br />
to comit:<br />
<code>git add .</code> &lt;=&gt; <code>git commit -a -m "description"</code> [commit -a =&gt; add]<br />
<b><i>WARNING</i></b>: if any new files are added to the project since the last commit, <i>git add</i> must be used</li></ul>
<p><b>merge the results back</b><br />
<code>git checkout master</code><br />
<code>git merge <i>name</i></code><br />
<ul><li>to delete the topic branch (it’s quite common to leave the topic branch intact):<br />
<code>git branch -d <i>name</i></code></li>
<li>to abandon the topic branch changes (the -D flag will delete the branch even though we haven’t merged in the changes):<br />
<code>git branch -D <i>name</i></code></li>
<li>after the first push, on most systems the origin master can be ommited:<br />
<code>git push</code><br /></p></li></ul></li>
<li><b>Deploying</b><br />
deploying (Rails applications used to be a pain) early and often allows us to catch any deployment problems early in our development cycle<br />
<ul><li>shared hosts or virtual private servers running Phusion Passenger (a module for the Apache and Nginx22 web servers)</li>
<li>full-service deployment companies such as <code>Engine Yard</code> and <code>Rails Machine</code></li>
<li>cloud deployment services such as <code>Engine Yard Cloud</code> and <code><b>Heroku</b></code></li></ul>
Heroku makes deploying Rails applications ridiculously easy—as long as your source code is under version control with Git
<p><b>Heroku setup</b><br />
Heroku uses the <code>PostgreSQL</code> database =&gt; need to add (at the end of the file) the pg gem in the production environment:
<code>sudo gedit Gemfile</code><br />
<i>group :production do<br />
&nbsp;&nbsp;&nbsp;&nbsp;gem 'pg', '0.12.2'<br />
end</i><br />
<code>bundle install --without production</code> (<i>--without production</i> prevents the local installation of any production gems)<br />
<ul><li>create Heroku account and confirm it (email)</li>
<li>[https://toolbelt.heroku.com/debian] <code>https://toolbelt.heroku.com/debian</code></li>
<li><code>heroku login</code> =&gt; Enter email/password<br />
=&gt; Found existing public key: /home/criedo/.ssh/id_rsa.pub [...]<br />
&nbsp;&nbsp;&nbsp;Authentication successful.</li>
<li>[cd ~/projects/RoRTutorial_HartlM] <code>heroku create</code> =&gt; Creating immense-shelf-3538... done, stack is cedar<br />
&nbsp;&nbsp;&nbsp;&nbsp;http://immense-shelf-3538.herokuapp.com/ | git@heroku.com:immense-shelf-3538.git<br>
&nbsp;&nbsp;&nbsp;&nbsp;Git remote heroku added<br />
<i>The heroku command line client will be installed into /usr/local/heroku and /usr/local/heroku/bin will be added to your PATH.</i><br />
<li><code>heroku --version</code> =&gt; <b>heroku-toolbelt/2.33.3 (x86_64-linux) ruby/1.9.3</b></li>
<li><code>git remote -v</code> =&gt;<br />
heroku	git@heroku.com:immense-shelf-3538.git (fetch)<br />
heroku	git@heroku.com:immense-shelf-3538.git (push)<br />
origin	git@github.com:criedo/RoRTutorial_HartlM.git (fetch)<br />
origin	git@github.com:criedo/RoRTutorial_HartlM.git (push)<br /></li>
<li>to associate a Git repo with an existing application (used with an existing Git repo to add a remote):<br />
<code>heroku git:remote -a <i>name</i></code></li>
<li>using origin as the remote name will allow you to type just <code>git push</code> instead of <code>git push heroku</code>, but we recommend using an explicitly named remote</li></ul>
<p><b>Change settings</b>:</p>
<i>Name</i>: criedo-ror-tutorial =&gt; Rename (button)<br />
<i>GitHub Repo</i>: criedo/RoRTutorial_HartlM.git =&gt; Save (button)<br />
<i>Domains</i>: criedo-ror-tutorial.herokuapp.com =&gt; Add (button) [Add your custom domains here then point your DNS to Heroku]<br />
<i>Error Pages</i>: Error URL (http://s3.amazonaws.com/heroku_pages/error.html); Maintenance URL (http://s3.amazonaws.com/heroku_pages/maintenance.html) =&gt; Save (button)</li>
<p><b>Deploy your code<b>:</p>
<code>git push heroku master</code> [https://devcenter.heroku.com/articles/rails3]<br />
&nbsp;&nbsp;&nbsp;&nbsp;=&gt; <i>ERROR</i> (!  No such app [name changed!]): <code>git remote rm heroku</code><br />
&nbsp;&nbsp;&nbsp;&nbsp;<code>git remote add heroku git@heroku.com:criedo-ror-tutorial.git</code>
&nbsp;&nbsp;&nbsp;&nbsp;<code>git push heroku master</code> =&gt; [...] http://criedo-ror-tutorial.herokuapp.com deployed to Heroku [...]<br />
<ul><li>[Ensure one dyno running: <code>heroku ps:scale web=1</code>] [For each application, Heroku provides 750 free dyno-hours]</li>
<li>Check the state of the app’s dynos:<br />
<code>heroku ps</code> =&gt; [...] web.1: up 2012/12/09 02:11:01 (~ 3m ago)</li>
<li>Visit the app in our browser:<br />
<code>heroku open</code> =&gt; open browser =&gt; page: Welcome aboard - You’re riding Ruby on Rails!<br />
&nbsp;&nbsp;&nbsp;&nbsp;<b><i>Warning</i></b>: [About your application’s environment] =&gt; We're sorry, but something went wrong.</li>
<li>View the logs: <code>heroku logs</code> =&gt; png host=criedo-ror-tutorial.herokuapp.com fwd=80.180.173.81 dyno=web.1 queue=0 wait=0ms connect=3ms service=12ms status=200 bytes=6646</li>
<li>Launch a Rails console process: <code>heroku run console</code></li>
<li>Rake can be run as an attached process exactly like the console: <code>heroku run rake db:migrate</code></li>
<li>Rails 3.1+ asset pipeline: several options when deploying to Heroku =&gt; [https://devcenter.heroku.com/articles/rails3x-asset-pipeline-cedar]</li></li></ul>
<p><b>Run on robust webserver Thin</p> (add it to Gemfile):<br />
<ul><li><code>sudo gedit Gemfile</code><br />
<i>gem 'thin'</i></li>
<li><code>bundle install</code></li>
<li>Change the command used to launch your web process by creating a file called Procfile:<br />
<code>echo "web: bundle exec rails server thin -p \$PORT -e \$RACK_ENV" > Procfile</code></li>
<li>Set the RACK_ENV to development:<br />
<code>echo "RACK_ENV=development" >>.env</code></li>
<li>Test your Procfile locally using Foreman:<br />
<code>foreman start</code> =&gt; 08:21:58 web.1  | started with pid 51496<br />
<b>into the browser</b>: <code>http://localhost:5000/</code> =&gt; Welcome aboard - You’re riding Ruby on Rails!
&nbsp;&nbsp;&nbsp;&nbsp;Ctrl+C =&gt; [...] Listening on 0.0.0.0:5000, CTRL+C to stop<br /></li>
<li>deploy your changes to Heroku<br />
<code>git add .<code><br />
<code>git commit -m "use thin via procfile"<code><br />
<code>git push heroku<code><br />
Check ps to see if the web process uses the new command specifying Thin as the webserver:<br />
<code>heroku ps</code> =&gt; web.1         starting for 3s     bundle exec rails server thin -p $..<br />
<li>Deploy your changes to Heroku:
<code>git add .</code><br />
<code>git commit -m "use thin via procfile"</code><br />
<code>git push heroku</code><br />
<li><b>Troubleshooting</b> (heroku ps shows state crashed): check log to find out what went wrong</li></ul>
</li>
</li>

<li><b></b><br />
<p><b>into the prompt</b>: <code></code></p>
<p><b>into the editor</b>: <i>edit</i> </p>
&nbsp;&nbsp;&nbsp;&nbsp;<b><i>Warning</i></b>: &lt;=&gt; =&gt; <i>ERROR</i>: 
</li>
</ul>
