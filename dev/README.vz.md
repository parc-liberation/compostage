## Building the Web Site

To build the web site locally, you can use Docker...

```
cd compostage
docker run --rm --label=jekyll --volume=$(pwd):/srv/jekyll -it -p 4000:4000 jekyll/jekyll jekyll serve
```

... or you can install [Jekyll](http://jekyllrb.com/) directly on your machine.  
Then, use...

* `bundle exec jekyll serve -w` to run a web server locally.
* `bundle exec jekyll build` to simply generate static HTML files.
* `sudo bundle install` to resolve problems about missing gems or dependencies.

When running, the web site can be browsed at [http://localhost:4000](http://localhost:4000).
In both cases, you can then use
`bundle exec htmlproofer ./_site --only-4xx --check-favicon --check-html --allow-hash-href --disable-external`
to verify the generated content.
