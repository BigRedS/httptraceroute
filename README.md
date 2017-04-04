# HTTPTraceroute

Given a URL, prints the chain of redirects as it follows it:

    $ httptraceroute news.bbc.co.uk
    total     this      socket                 server                         code meaning                 nexthop
    0.1146ms  0.1146ms  212.58.246.80:80       Apache                         301  Moved Permanently       http://www.bbc.co.uk/news/
    0.1768ms  0.0622ms  212.58.244.70:80       Apache                         301  Moved Permanently       /news
    0.1772ms  0.0003ms                                                        400  Bad Request



## Usage:

        httptraceroute [options] url
    
    Options:
    
    These will cause httptraceroute to make one single request before exiting:
    
      --first-status                Only the numeric HTTP status returned from <url>
      --first-url                   The redirected-to URL returned from the request to <url>
      --first-header <header-name>  The value of <header-name> returned by the first host.
                                    empty if unset.
    
    And these will display how the last hosts in the chain responded:
    
      --last-status                Only the numeric HTTP status from the last hop
      --last-url                   The last redirected-to URL (the eventual point a visitor
                                   would reach); this is returned by the *penultimate* host.
      --last-header <header-name>  The value of <header-name> returned by the last host.
                                   empty if unset.

