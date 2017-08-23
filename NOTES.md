
    git clone git@github.com:twitwi/KaTeX.git
    cd KaTeX
    git remote add Khan--KaTeX https://github.com/Khan/KaTeX.git
    git fetch Khan--KaTeX 
    git merge Khan--KaTeX/master 
    git fetch --tags Khan--KaTeX
    git checkout v0.8.2 -b 0.8.2-fordeckjs
    
    # then patch as desired
    
    git commit -m 'Patch for deck.js cdn \n\n defaulting fonts loading to a cdn (so people can either download them locally or have an internet connection)'
    
    make

    rm -rf ../deck.js/extensions/katex/fonts/
    cp -r build/fonts/../deck.js/extensions/katex/
    cp -r build/fonts/ ../deck.js/extensions/katex/
    \cp -t ../deck.js/extensions/katex/ build/katex.min.{js,css}
       
       
