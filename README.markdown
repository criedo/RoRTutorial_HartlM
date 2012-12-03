<h2>Tutorial: Ruby on Rails - Learn Web Development with Rails<br />
&nbsp;&nbsp;&nbsp;Michael Hartl<br />
&nbsp;&nbsp;&nbsp;<code>http://ruby.railstutorial.org/ruby-on-rails-tutorial-book</code><br />
&nbsp;&nbsp;&nbsp;<code>=> https://github.com/criedo/RoRTutorial_HartlM</code></h2>
<br />
<b>ruby -v</b> => ruby 1.9.3p327 (2012-11-10 revision 37606) [x86_64-linux]<br />
<b>gem -v</b> => 1.8.24<br />
<b>rails -v</b> => Rails 3.2.9<br />
<br />
<b>ruby_path</b>: ./home/criedo/.rvm/rubies/ruby-1.9.3-p327/bin<br />
<b>project_path</b>: [cd ~/projects/RoRTutorial_HartlM]<br />
&nbsp;&nbsp;&nbsp;<code>cd ~/projects<br />
&nbsp;&nbsp;&nbsp;sudo mkdir RoRTutorial_HartlM<br />
&nbsp;&nbsp;&nbsp;sudo chmod a=rx RoRTutorial_HartlM<br />
&nbsp;&nbsp;&nbsp;sudo chmod u+w RoRTutorial_HartlM<br />
&nbsp;&nbsp;&nbsp;cd RoRTutorial_HartlM<br />
&nbsp;&nbsp;&nbsp;sudo gedit README.markdown<br />
&nbsp;&nbsp;&nbsp;sudo chmod a=rw README.markdown</code><br />
<br />
<h3>Chapter 1 From zero to deploy</h3>
<ul>
<li><b>download</b>: 'The Well Grounded Rubyist - Black, David A. (2009)'<br />
&nbsp;&nbsp;from http://ebookbrowse.com/gdoc.php?id=364567597&url=b710df116262f74a213890c609318019<br />
&nbsp;&nbsp;=> C:\Download\prog\ruby\tutorial\The Well Grounded Rubyist - Black - Manning (2009).pdf</li>
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
<code>rvm use 1.9.3@rails3tutor --create --default<br />
which gem => <i>/home/criedo/.rvm/rubies/ruby-1.9.3-p327/bin/gem</i><br />
sudo gedit ~/.gemrc</code><br />
&nbsp;&nbsp;install: --no-rdoc --no-ri<br />
&nbsp;&nbsp;update: --no-rdoc --no-ri<br />
<code>gem install rails -v 3.2.9<br />
rails -v => <i>Rails 3.2.9</i><br />
sudo apt-get install libxslt-dev libxml2-dev libsqlite3-dev => <i>0 upgraded, 0 newly installed, 0 to remove and 0 not upgraded.</i><br />
rails new first_app => <i>Your bundle is complete! Use `bundle show [gemname]` to see where a bundled gem is installed.</i><br />
cd first_app/<br />
sudo gedit Gemfile</code><br />
&nbsp;&nbsp;<i>source 'https://rubygems.org'<br />
&nbsp;&nbsp;<br />
&nbsp;&nbsp;gem 'rails', '3.2.9'<br />
&nbsp;&nbsp;<br />
&nbsp;&nbsp;group :development do<br />
&nbsp;&nbsp;gem 'sqlite3', '1.3.5' [previous: 1.3.6]<br />
&nbsp;&nbsp;end<br />
&nbsp;&nbsp;<br />
&nbsp;&nbsp;# Gems used only for assets and not required in production environments by default.<br />
&nbsp;&nbsp;group :assets do<br />
&nbsp;&nbsp;  gem 'sass-rails',   '3.2.5'<br />
&nbsp;&nbsp;  gem 'coffee-rails', '3.2.2'<br />
&nbsp;&nbsp;  <br />
&nbsp;&nbsp;  gem 'uglifier', '1.2.3' [previous: 1.3.0]<br />
&nbsp;&nbsp;	end<br />
&nbsp;&nbsp;<br />
&nbsp;&nbsp;gem 'jquery-rails', '2.0.2' [previous: 2.1.4]</i><br />
<code>bundle install<br />
rails server => <i>ERROR: Could not find a JavaScript runtime</i><br />
sudo apt-get install nodejs<br />
rails server => <i>[2012-12-02 14:54:49] INFO  WEBrick[ 1.3.1]::HTTPServer#start: pid=6239 port=3000</i></code><br />
<p>into the browser</b>: <code>http://localhost:3000/</code></p></li>
<li><b>installing Git</b><br />
	<code>git config --global user.name "criedo"<br />
	git config --global user.email cfriedo@yahoo.com<br />
	git config --global alias.co checkout<br />
	git config --global core.editor "sudo gedit"<br />
	git config --list => <i>user.name ...</i><br />
	git init => <i>Initialized empty Git repository in /home/criedo/projects/RoRTutorial_HartlM/.git/</i><br />
	sudo gedit .gitignore<br />
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
	git add .<br />
	git status => <i># On branch master [...]</i><br />
	git commit -m "Initial commit" => <i>[master (root-commit) 8aa5dcf] Initial commit - 38 files changed, 1265 insertions(+) [...]</i><br />
		<b><i>important to note that Git commits are local</i></b><br />
	git log => <i>commit 8aa5dcfd8135afe0d94d6d2b06447a148451e477 [...]</i><br />
		<b><i>undo the changes by having Git check out the previous commit with the checkout command (-f flag to force overwriting the current changes)</i></b></code><br />
	<p><b>Generating SSH Keys</b> [https://help.github.com/articles/generating-ssh-keys#]</p>
	<code>ssh-keygen -t rsa -C "cfriedo@yahoo.com"
		<i>Enter file in which to save the key (/home/criedo/.ssh/id_rsa): [Enter]<br />
		Enter passphrase (empty for no passphrase):crfr97<br />
		Enter same passphrase again:crfr97<br />
		=> The key fingerprint is: 04:d9:79:bc:9e:f8:dc:bf:2a:e6:d6:77:2c:52:ad:77 cfriedo@yahoo.com</i><br />
	sudo apt-get install xclip<br />
	xclip -sel clip < ~/.ssh/id_rsa.pub</code><br />
	<p>into the browser</b>: https://github.com/<br />
	<i>Go to your Account Settings<br />
	Click "SSH Keys" in the left sidebar<br />
	Click "Add SSH key"<br />
	Paste your key into the "Key" field<br />
	Click "Add key"<br />
	Confirm the action by entering your GitHub password</i></p>
	<code>ssh -T git@github.com</code><br />
		=> <i>The authenticity of host 'github.com (207.97.227.239)' can't be established.<br />
		# RSA key fingerprint is 16:27:ac:a5:76:28:2d:36:63:1b:56:4d:eb:df:a6:48.<br />
		# Are you sure you want to continue connecting (yes/no)?</i><code>yes [Enter]</code><br />
		<i>Hi criedo! You've successfully authenticated, but GitHub does not provide shell access.</i><br />
	<code>git remote add origin git@github.com:criedo/RoRTutorial_HartlM.git<br />
	git push -u origin master<br />
		=> <i>ERROR: github [rejected] master -> master (non-fast-forward) error [https://help.github.com/articles/dealing-with-non-fast-forward-errors]<br />
	git push -u origin master --force => <i>Writing objects: 100% (64/64), 27.15 KiB, done.</i></code>
</li>
<li><b></b><br />
<p>into the prompt</b>: <code></code></p>
<p><b>into the editor</b>: <i>edit</i> </p>
[<b><i>Warning</i></b>: ]
</li>
</ul>
