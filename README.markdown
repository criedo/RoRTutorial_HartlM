<h2>Tutorial: Ruby on Rails - Learn Web Development with Rails - Michael Hartl<br />
	<code>http://ruby.railstutorial.org/ruby-on-rails-tutorial-book<br />
	=> https://github.com/criedo/RoRTutorial_HartlM</code></h2>
<br />
<b>ruby -v  </b>=> <code>=> ruby 1.9.3p327 (2012-11-10 revision 37606) [x86_64-linux]</code><br />
<b>gem -v   </b>=> 1.8.24</code><br />
<b>rails -v </b>rails -v => Rails 3.2.9</code><br />
<br />
<b>ruby_path</b>:    ./home/criedo/.rvm/rubies/ruby-1.9.3-p327/bin<br />
<b>project_path</b>: [cd ~/projects/RoRTutorial_HartlM]<br />
	<code>cd ~/projects<br />
	sudo mkdir RoRTutorial_HartlM<br />
	sudo chmod a=rx RoRTutorial_HartlM<br />
	sudo chmod u+w RoRTutorial_HartlM<br />
	cd RoRTutorial_HartlM<br />
	sudo gedit README.markdown<br />
	sudo chmod a=rw README.markdown</code><br />
<br />
<h3>Chapter 1 From zero to deploy</h3>
<ul>
<li>downloaded 'The Well Grounded Rubyist - Black, David A. (2009)'<br />
	from http://ebookbrowse.com/gdoc.php?id=364567597&url=b710df116262f74a213890c609318019<br />
	=> C:\Download\prog\ruby\tutorial\The Well Grounded Rubyist - Black - Manning (2009).pdf</li>
<li>links:<br />
	http://railsforzombies.org/<br />
	http://tryruby.org/levels/1/challenges/0<br />
	http://railscasts.com/<br />
	http://guides.rubyonrails.org/<br />
	[scaling] http://idleprocess.wordpress.com/2009/11/24/presentation-summary-high-performance-at-massive-scale-lessons-learned-at-facebook/<br />
	[ide] RadRails => http://www.aptana.com/products/radrails<br />
	[ide] RubyMine => http://www.jetbrains.com/ruby/buy/index.jsp [Commercial License: €142; Personal License: €66; Open Source Project License: Free]<br />
	[ide] 3rd Rail => http://www.embarcadero.com/products/3rdrail [RAD Studio: €5,115.81]<br />
	[editor] Sublime Text 2 => http://www.sublimetext.com/2 [US$59] [https://github.com/mhartl/rails_tutorial_sublime_text]<br />
	[editor] vim => http://www.vim.org/</li>
<li><i>installing RVM</i>: convenient to create separate gemsets, which are self-contained bundles of gems<br />
	<code>rvm use 1.9.3@rails3tutor --create --default<br />
	which gem => <i>/home/criedo/.rvm/rubies/ruby-1.9.3-p327/bin/gem</i><br />
	sudo gedit ~/.gemrc<br />
		install: --no-rdoc --no-ri<br />
		update: --no-rdoc --no-ri<br />
	gem install rails -v 3.2.9<br />
	rails -v => <i>Rails 3.2.9</i><br />
	sudo apt-get install libxslt-dev libxml2-dev libsqlite3-dev => <i>0 upgraded, 0 newly installed, 0 to remove and 0 not upgraded.</i><br />
	rails new first_app => <i>Your bundle is complete! Use `bundle show [gemname]` to see where a bundled gem is installed.</i><br />
	cd first_app/<br />
	sudo gedit Gemfile<br />
		<i>source 'https://rubygems.org'<br />
		gem 'rails', '3.2.9'<br />
		group :development do<br />
		  gem 'sqlite3', '1.3.5'<br />
		end<br />
		# Gems used only for assets and not required in production environments by default.<br />
		group :assets do<br />
		  gem 'sass-rails',   '3.2.5'<br />
		  gem 'coffee-rails', '3.2.2'<br />
		  gem 'uglifier', '1.2.3'<br />
		end<br />
		gem 'jquery-rails', '2.0.2'</i><br />
	bundle install</code>
</li>
<li><b></b><br />
<p>into the prompt</b>: <code></code></p>
<p><b>into the editor</b>: <i>edit</i> </p>
[<b><i>Warning</i></b>: ]
</li>
</ul>
