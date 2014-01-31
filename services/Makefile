VALIDATOR := perl ../utils/validator.pl --schema spore_validation.rx --description
SPORE2DOT := perl ../utils/spore2dot.pl

check: spore_validation.rx
	@${MAKE} -C github check
	@${MAKE} -C googlemaps check
	@${MAKE} -C linkedin check
	@$(VALIDATOR) amazons3.json
	@$(VALIDATOR) backtweet.json
	@$(VALIDATOR) backtype.json
	@$(VALIDATOR) btce.json
	@$(VALIDATOR) bter.json
	@$(VALIDATOR) bitly.json
	@$(VALIDATOR) datapublica.json
	@$(VALIDATOR) facebook_graph.json
	@$(VALIDATOR) github.json
	@$(VALIDATOR) gnip.json
	@$(VALIDATOR) googlemaps.json
	@$(VALIDATOR) googleoauth.json
	@$(VALIDATOR) googleoauth2.json
	@$(VALIDATOR) googlepagespeed.json
	@$(VALIDATOR) googleshortener.json
	@$(VALIDATOR) googletranslate.json
	@$(VALIDATOR) ihackernews.json
	@$(VALIDATOR) intervals.json
	@$(VALIDATOR) klout.json
	@$(VALIDATOR) ohloh.json
	@$(VALIDATOR) topsy.json
	@$(VALIDATOR) twitter.json
	@$(VALIDATOR) twitter_search.json
	@$(VALIDATOR) virwox.json
	@$(VALIDATOR) voipms.json
	@$(VALIDATOR) intervals.json

test: check

spore_validation.rx:
	wget https://raw.github.com/SPORE/specifications/master/spore_validation.rx

png: \
    amazons3.png \
    backtweet.png \
    backtype.png \
    bitly.png \
    btce.png \
    bter.png \
    datapublica.png \
    facebook_graph.png \
    github.png \
    gnip.png \
    googlemaps.png \
    googleoauth.png \
    googleoauth2.png \
    googlepagespeed.png \
    googleshortener.png \
    googletranslate.png \
    ihackernews.png \
    indextank.png \
    intervals.png \
    klout.png \
    ohloh.png \
    topsy.png \
    twitter.png \
    twitter_search.png \
    virwox.png \
    voipms.png

	@${MAKE} -C github png
	@${MAKE} -C googlemaps png
	@${MAKE} -C linkedin png

%.png : %.dot
	dot -T png -o $@ $<

%.dot: %.json
	$(SPORE2DOT) $< > $@

clean:
	@${MAKE} -C github clean
	@${MAKE} -C googlemaps clean
	@${MAKE} -C linkedin clean
	-rm *.png *.dot spore_validation.rx
