## Building the Web Site

### With Docker

Run...

```
cd compostage
docker run --rm --label=jekyll \
           --volume=$(pwd):/srv/jekyll \
           --volume="$PWD/dev/bundles:/usr/local/bundle" \
           --name compostage \
           -it -p 4000:4000 jekyll/jekyll:3.8.5 jekyll serve \
           --config _config.yml,_dev.config.yml
```

The web site can then be browsed at [http://localhost:4000](http://localhost:4000).  
To inspect the container, use...

```
docker exec -ti compostage /bin/bash
```

To verify the generated content, use...

```
docker exec -ti compostage bundle exec htmlproofer ./_site --only-4xx --check-favicon --check-html --allow-hash-href --disable-external
```

### On your machine

You can install [Jekyll](http://jekyllrb.com/) directly on your machine.  
Then, use...

* `bundle exec jekyll serve -w` to run a web server locally.
* `bundle exec jekyll build` to simply generate static HTML files.
* `sudo bundle install` to resolve problems about missing gems or dependencies.

The web site can be browsed at [http://localhost:4000](http://localhost:4000).
To verify the generated content, use...

```
bundle exec htmlproofer ./_site --only-4xx --check-favicon --check-html --allow-hash-href --disable-external
```
