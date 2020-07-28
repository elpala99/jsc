
# Table of Contents

1.  [MINIMAL INSTALLATION](#org263a74c)
    1.  [FIXES](#org75d5ad6)


<a id="org263a74c"></a>

# MINIMAL INSTALLATION

In this section, the minimum packages and fixes that I use for my system can be
found. For each package, the depedencies are shown and most of the packages are
built from source to extract the newest version. This was done for Ubuntu 18.04
LTS.


<a id="org75d5ad6"></a>

## FIXES

1.  Fix right click
    -   Install gnome-tweaks with apt (3.28.1)
    -   Change mouse emulation to Area
2.  Fix broken dependencies
    -   sudo apt &#x2013;fix-broken install
3.  Fix Brightness controls:
    -   Intel Driver:
        -   Write file /etc/X11/xorg.conf
            
            <p class="verse">
            Section &ldquo;Device&rdquo;<br />
            &#xa0;&#xa0;Identifier  &ldquo;Intel Graphics&rdquo;<br />
            &#xa0;&#xa0;Driver      &ldquo;intel&rdquo;<br />
            &#xa0;&#xa0;Option      &ldquo;Backlight&rdquo;  &ldquo;intel<sub>backlight</sub>&rdquo;<br />
            EndSection<br />
            </p>
    -   Nvidia driver:
        -   Install light tool from the following git
        -   git clone <https://github.com/haikarainen/light.git>
4.  HDMI output (Tested for Acer Nitro 5)
    -   Install new drivers from nvidia.

WINDOW MANAGER

1.  i3 with apt (4.17.1)
2.  i3-gaps (4.17.1)
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">sudo add-apt-repository ppa:kgilmer/speed-ricer</td>
    </tr>
    
    
    <tr>
    <td class="org-left">sudo apt update</td>
    </tr>
    
    
    <tr>
    <td class="org-left">sudo apt install i3-gaps</td>
    </tr>
    </tbody>
    </table>
3.  qtile (0.15.1)
    
    -   libxcb-render0-dev
    -   libffi-dev
    -   libcairo2
    -   libpangocairo-1.0-0
    -   libgirepository1.0-dev
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">python3.8 -m venv src/python-envs/qtile-env</td>
    </tr>
    
    
    <tr>
    <td class="org-left">source src/python-envs/qtile-env/bin/activate</td>
    </tr>
    
    
    <tr>
    <td class="org-left">pip install xcffib && sudo pip install cairocffi</td>
    </tr>
    
    
    <tr>
    <td class="org-left">pip install PyGObject dbus-python</td>
    </tr>
    
    
    <tr>
    <td class="org-left">pip install qtile</td>
    </tr>
    </tbody>
    </table>

APPS

1.  st (0.8.3)
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">git clone <https://github.com/juanscr/st></td>
    </tr>
    
    
    <tr>
    <td class="org-left">cd st && sudo make clean install</td>
    </tr>
    </tbody>
    </table>
2.  brave (1.8.96)
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">sudo apt install apt-transport-https curl</td>
    </tr>
    
    
    <tr>
    <td class="org-left">curl -s <https://brave-browser-apt-release.s3.brave.com/brave-core.asc></td>
    </tr>
    </tbody>
    </table>
    
    sudo apt-key &#x2013;keyring /etc/apt/trusted.gpg.d/brave-browser-release.gpg add -
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">echo &ldquo;deb [arch=amd64] <https://brave-browser-apt-release.s3.brave.com/> stable main&rdquo;</td>
    </tr>
    </tbody>
    </table>
    
    sudo tee /etc/apt/sources.list.d/brave-browser-release.list
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">sudo apt update</td>
    </tr>
    
    
    <tr>
    <td class="org-left">sudo apt install brave-browser</td>
    </tr>
    </tbody>
    </table>
3.  okular with apt (1.3.3)
4.  spotify (spotify 1.1.26)
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">; Install latest version from</td>
    </tr>
    </tbody>
    </table>
    
    <http://repository.spotify.com/pool/non-free/s/spotify-client/> ;
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">sudo chmod a+wr /usr/share/spotify</td>
    </tr>
    
    
    <tr>
    <td class="org-left">sudo chmod a+wr /usr/share/spotify/Apps -R</td>
    </tr>
    
    
    <tr>
    <td class="org-left">curl -fsSL <https://raw.githubusercontent.com/khanhas/spicetify-cli/master/install.sh></td>
    <td class="org-left">sh</td>
    </tr>
    
    
    <tr>
    <td class="org-left">mv  ~/spicetify-cli /opt</td>
    </tr>
    
    
    <tr>
    <td class="org-left">cd /usr/local/bin && ln -s /opt/spicetify-cli/spicetify</td>
    </tr>
    </tbody>
    </table>
5.  emacs (26.3)
    
    -   libx11-dev
    -   libxpm-dev
    -   libjpeg-dev
    -   libpng-dev
    -   libgif-dev
    -   libtiff-dev
    -   libgtk2.0-dev
    -   libtinfo-dev
    -   libncurses5-dev
    -   automake
    -   autoconf
    -   libgnutls28-dev
    -   mailutils
    -   libxaw7-dev
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">; Go to Ecuador Mirror and download tar ;</td>
    </tr>
    
    
    <tr>
    <td class="org-left">./configure &#x2013;with-x-toolkit=lucid</td>
    </tr>
    
    
    <tr>
    <td class="org-left">sudo make</td>
    </tr>
    
    
    <tr>
    <td class="org-left">sudo make install</td>
    </tr>
    </tbody>
    </table>
6.  doom emacs (2.0.9)
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">git clone &#x2013;depth 1 <https://github.com/hlissner/doom-emacs> ~/.emacs.d</td>
    </tr>
    
    
    <tr>
    <td class="org-left">~/.emacs.d/bin/doom install</td>
    </tr>
    
    
    <tr>
    <td class="org-left">; Run in emacs ;</td>
    </tr>
    
    
    <tr>
    <td class="org-left">M-x all-the-icons-install-fonts</td>
    </tr>
    </tbody>
    </table>
7.  pavucontrol with apt (3.0)
8.  zathura with apt (0.3.8)
9.  sxiv (26.0)
    
    -   libexif-dev
    -   fontconfig
    -   freetype2-demos
    -   libimlib2-dev
    -   libxft-dev
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">; Download tar from <https://github.com/muennich/sxiv> ;</td>
    </tr>
    
    
    <tr>
    <td class="org-left">; Untar folder and move to .config ;</td>
    </tr>
    
    
    <tr>
    <td class="org-left">sudo make clean install</td>
    </tr>
    </tbody>
    </table>

I3 RELATED STUFF:

1.  feh with apt (2.23.2)
2.  scrot with apt (0.8)
3.  betterlockscreen
    
    -   libxcb-randr0-dev
    -   libxcb-xrm-dev
    -   libev-dev
    -   libxcb-xinerama0-dev
    -   libxcb-xkb-dev
    -   libxcb-composite0-dev
    -   libxcb-image0-dev
    -   libxkbcommon-dev
    -   libxkbcommon-x11-dev
    -   libpam-cracklib
    -   libpam-doc
    -   libpam-modules
    -   libpam-modules-bin
    -   libpam-runtime
    -   libpam0g-dev
    -   checkinstall
    -   i3lock-color
        -   git clone <https://github.com/PandorasFox/i3lock-color>
        -   git tag -f &ldquo;git-$(git rev-parse &#x2013;short HEAD)&rdquo;
        -   autoreconf -i && ./configure && make
        -   sudo checkinstall &#x2013;pkgname=i3lock-color &#x2013;pkgversion=1 -y
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">git clone <https://github.com/pavanjadhaw/betterlockscreen></td>
    </tr>
    
    
    <tr>
    <td class="org-left">sudo cp betterlockscreen /usr/local/bin</td>
    </tr>
    </tbody>
    </table>
4.  compton with apt (0.1)
5.  xclip with apt (0.12)
6.  polybar (3.4.3)
    
    -   xcb-proto
    -   cmake
    -   libpulse-dev
    -   libjsoncpp-dev
    -   libxcb-xkb-dev
    -   libxcb-xrm-dev
    -   libxcb-cursor-dev
    -   libmpdclient-dev
    -   libnl-genl-3-dev
    -   pkg-config
    -   python3-sphinx
    -   libcairo2-dev
    -   libxcb1-dev
    -   libxcb-util0-dev
    -   libxcb-randr0-dev
    -   libxcb-composite0-dev
    -   python-xcbgen
    -   libxcb-image0-dev
    -   libxcb-ewmh-dev
    -   libxcb-icccm4-dev
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">; Download tar from git page ;</td>
    </tr>
    
    
    <tr>
    <td class="org-left">./build.sh</td>
    </tr>
    
    
    <tr>
    <td class="org-left">Spotify module</td>
    </tr>
    
    
    <tr>
    <td class="org-left"><https://github.com/mihirlad55/polybar-spotify-module></td>
    </tr>
    
    
    <tr>
    <td class="org-left">sudo apt install libdbus-1-dev</td>
    </tr>
    
    
    <tr>
    <td class="org-left">systemctl &#x2013;user enable spotify-listener</td>
    </tr>
    
    
    <tr>
    <td class="org-left">systemctl &#x2013;user start spotify-listener</td>
    </tr>
    </tbody>
    </table>

Packages:

1.  python (3.8.3)
    
    -   build-essential
    -   zlib1g-dev
    -   libffi-dev
    -   libreadline-gplv2-dev
    -   libncursesw5-dev
    -   libssl-dev
    -   libsqlite3-dev
    -   tk-dev
    -   libgdbm-dev
    -   libc6-dev
    -   libbz2-dev
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">; Download tar from python page. ;</td>
    </tr>
    
    
    <tr>
    <td class="org-left">./configure &#x2013;enable-optimizations</td>
    </tr>
    
    
    <tr>
    <td class="org-left">sudo make</td>
    </tr>
    
    
    <tr>
    <td class="org-left">sudo make install</td>
    </tr>
    </tbody>
    </table>
2.  texlive (2017.20180305)
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">sudo apt install texlive-full</td>
    </tr>
    </tbody>
    </table>
3.  ghcup (0.1.5)
    
    -   curl
    -   libgmp-dev
    -   libncurses-dev
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">curl &#x2013;proto &rsquo;=https&rsquo; &#x2013;tlsv1.2 -sSf <https://get-ghcup.haskell.org></td>
    <td class="org-left">sh</td>
    </tr>
    </tbody>
    </table>
4.  agda (2.6.1)
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">cabal update</td>
    </tr>
    
    
    <tr>
    <td class="org-left">cabal install Agda</td>
    </tr>
    
    
    <tr>
    <td class="org-left">agda-mode setup</td>
    </tr>
    </tbody>
    </table>
5.  git with apt (2.17.1)
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">git config &#x2013;global credential.helper store</td>
    </tr>
    
    
    <tr>
    <td class="org-left">git config &#x2013;global core.editor &ldquo;nvim&rdquo;</td>
    </tr>
    </tbody>
    </table>
6.  R (3.6.1)
    
    -   gfortran
    -   libcurl4-openssl-dev
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">; Download tar ball from R webpage. ;</td>
    </tr>
    
    
    <tr>
    <td class="org-left">./configure &#x2013;enable-R-shlib</td>
    </tr>
    
    
    <tr>
    <td class="org-left">sudo make</td>
    </tr>
    
    
    <tr>
    <td class="org-left">sudo make install</td>
    </tr>
    </tbody>
    </table>

\################### ADD ONS AND COSMETHIC ########################
; COSMETHIC ;

1.  Theme
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">Install lxappeareance (0.6.3)</td>
    </tr>
    
    
    <tr>
    <td class="org-left">Select desired theme.</td>
    </tr>
    
    
    <tr>
    <td class="org-left">Download Moka Icons.</td>
    </tr>
    
    
    <tr>
    <td class="org-left">sudo add-apt-repository -u ppa:snwh/ppa</td>
    </tr>
    
    
    <tr>
    <td class="org-left">sudo apt install moka-icon-theme faba-icon-theme faba-mono-icons</td>
    </tr>
    
    
    <tr>
    <td class="org-left">Download Papirus Icons (recomended)</td>
    </tr>
    
    
    <tr>
    <td class="org-left">sudo add-apt-repository ppa:papirus/papirus</td>
    </tr>
    
    
    <tr>
    <td class="org-left">sudo apt update</td>
    </tr>
    
    
    <tr>
    <td class="org-left">sudo apt install papirus-icon-theme</td>
    </tr>
    
    
    <tr>
    <td class="org-left">Apply icon theme.</td>
    </tr>
    </tbody>
    </table>
2.  Load images at Pictures/wallpapers for random Background.
3.  Fonts
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">Install Font-Awesome from:</td>
    </tr>
    
    
    <tr>
    <td class="org-left"><https://fontawesome.com/how-to-use/on-the-desktop/setup/getting-started></td>
    </tr>
    
    
    <tr>
    <td class="org-left">Move otf files to ~/.local/share/fonts/</td>
    </tr>
    </tbody>
    </table>

APPS:

1.  vlc with apt (3.0.8)
2.  ; Pycharm ;
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">Download tar</td>
    </tr>
    
    
    <tr>
    <td class="org-left">Move folder to *opt*</td>
    </tr>
    
    
    <tr>
    <td class="org-left">Add to path</td>
    </tr>
    </tbody>
    </table>
3.  ; Popcorn Time ;
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">sudo apt update && sudo apt install libcanberra-gtk-module libgconf-2-4</td>
    </tr>
    
    
    <tr>
    <td class="org-left">Install tar from active website.</td>
    </tr>
    
    
    <tr>
    <td class="org-left">Put it in *opt*</td>
    </tr>
    
    
    <tr>
    <td class="org-left">Add to path</td>
    </tr>
    </tbody>
    </table>
4.  libreoffice with apt (6.4.1)
5.  arandr with apt (0.1.19)
6.  inkscape with apt (0.92.3)
    &#x2013; EXTENSION: textext (0.11)
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">sudo apt install python2.7</td>
    </tr>
    
    
    <tr>
    <td class="org-left">sudo apt install python-gtk2 python-gtksourceview2</td>
    </tr>
    
    
    <tr>
    <td class="org-left">sudo apt install pdf2svg</td>
    </tr>
    
    
    <tr>
    <td class="org-left">; Download tar from github <https://github.com/textext/textext/releases> ;</td>
    </tr>
    
    
    <tr>
    <td class="org-left">python2 setup.py</td>
    </tr>
    </tbody>
    </table>
7.  pdftk with snap (2.02)
8.  teams (1.3.0)
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">; Download deb from page ;</td>
    </tr>
    </tbody>
    </table>
9.  natron (2.3.14)
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">; Download tgz from page ;</td>
    </tr>
    
    
    <tr>
    <td class="org-left">; Run installer ;</td>
    </tr>
    </tbody>
    </table>
10. netlogo (6.1.1)
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">; Download tgz from page ;</td>
    </tr>
    
    
    <tr>
    <td class="org-left">; Move to opt ;</td>
    </tr>
    </tbody>
    </table>
11. repast symphony (2.7)
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">sudo apt install openjdk-8-jdk</td>
    </tr>
    
    
    <tr>
    <td class="org-left">; Downaload Eclipse Commiters (2019.06) from page ;</td>
    </tr>
    
    
    <tr>
    <td class="org-left">; Move it to opt ;</td>
    </tr>
    
    
    <tr>
    <td class="org-left">; Using Eclipse install Eclipse Groovy Development tools and Groovy Compile 2.4 (only) ;</td>
    </tr>
    
    
    <tr>
    <td class="org-left">; Install repast using Eclipse ;</td>
    </tr>
    
    
    <tr>
    <td class="org-left">; Install vim plugin in plugin section ;</td>
    </tr>
    </tbody>
    </table>
12. discord with snap (0.0.10)
13. stremio (4.4)
    
    -   qml-module-qtwebengine
    -   qml-module-qtwebchannel
    -   qml-module-qt-labs-platform
    -   libmpv1
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">; Download deb from page ;</td>
    </tr>
    </tbody>
    </table>
14. R-studio (1.2.5019)
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">; Install deb from web. ;</td>
    </tr>
    
    
    <tr>
    <td class="org-left">sudo dpkg &#x2013;ignore-depends=libclang-dev -i rstudio-1.2.5019-amd64.deb</td>
    </tr>
    
    
    <tr>
    <td class="org-left">sudo apt install -f</td>
    </tr>
    </tbody>
    </table>
15. chrome (80.0)
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">sudo nano /etc/apt/sources.list.d/google-chrome.list</td>
    </tr>
    
    
    <tr>
    <td class="org-left">deb [arch=amd64] <http://dl.google.com/linux/chrome/deb/> stable main</td>
    </tr>
    
    
    <tr>
    <td class="org-left">wget <https://dl.google.com/linux/linux_signing_key.pub></td>
    </tr>
    
    
    <tr>
    <td class="org-left">sudo apt-key add linux<sub>signing</sub><sub>key.pub</sub></td>
    </tr>
    
    
    <tr>
    <td class="org-left">sudo apt update</td>
    </tr>
    
    
    <tr>
    <td class="org-left">rm linux<sub>signing</sub><sub>key.pub</sub></td>
    </tr>
    
    
    <tr>
    <td class="org-left">sudo apt install google-chrome-stable</td>
    </tr>
    </tbody>
    </table>
16. ; virtualbox (6.1) ;
    
    -   libqt5opengl5
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">Download deb from <https://www.virtualbox.org/wiki/Linux_Downloads></td>
    </tr>
    </tbody>
    </table>

PACKAGES:

1.  xrandr (7.7)
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">sudo apt install x11-xserver-utils</td>
    </tr>
    </tbody>
    </table>
2.  wine (4.17)
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">sudo dpkg &#x2013;add-architecture i386</td>
    </tr>
    
    
    <tr>
    <td class="org-left">wget -nc <https://dl.winehq.org/wine-builds/winehq.key></td>
    </tr>
    
    
    <tr>
    <td class="org-left">sudo apt-key add winehq.key</td>
    </tr>
    
    
    <tr>
    <td class="org-left">sudo apt-add-repository &rsquo;deb <https://dl.winehq.org/wine-builds/ubuntu/> bionic main&rsquo;</td>
    </tr>
    
    
    <tr>
    <td class="org-left">sudo add-apt-repository ppa:cybermax-dexter/sdl2-backport</td>
    </tr>
    
    
    <tr>
    <td class="org-left">sudo apt update</td>
    </tr>
    
    
    <tr>
    <td class="org-left">sudo apt install &#x2013;install-recommends winehq-stable</td>
    </tr>
    </tbody>
    </table>
3.  jupyter notebook (2.0.1)
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">sudo pip install jupyterlab</td>
    </tr>
    </tbody>
    </table>
4.  java (11.0.6)
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">sudo apt install default-jdk</td>
    </tr>
    </tbody>
    </table>

; BACKUPS: ;

1.  dotfiles (Based on <https://www.atlassian.com/git/tutorials/dotfiles>)
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">Startup:</td>
    </tr>
    
    
    <tr>
    <td class="org-left">git init &#x2013;bare $HOME/folder/to/dotfiles</td>
    </tr>
    
    
    <tr>
    <td class="org-left">Add in bashrc:</td>
    </tr>
    
    
    <tr>
    <td class="org-left">alias dfiles=&rsquo;/usr/bin/git &#x2013;git-dir=$HOME/folder/to/dotfiles &#x2013;work-tree=$HOME&rsquo;</td>
    </tr>
    
    
    <tr>
    <td class="org-left">dfiles config &#x2013;local status.showUntrackedFiles no</td>
    </tr>
    
    
    <tr>
    <td class="org-left">dfiles remote add origin <git-link></td>
    </tr>
    
    
    <tr>
    <td class="org-left">dfiles push &#x2013;set-upstream origin master</td>
    </tr>
    
    
    <tr>
    <td class="org-left">Backup:</td>
    </tr>
    
    
    <tr>
    <td class="org-left">Add to the gitignore the folder your going to clone the git.</td>
    </tr>
    
    
    <tr>
    <td class="org-left">Check that the alias exists.</td>
    </tr>
    
    
    <tr>
    <td class="org-left">git clone &#x2013;bare <git-link> $HOME/folder/to/dotfiles</td>
    </tr>
    
    
    <tr>
    <td class="org-left">dfiles config &#x2013;local status.showUntrackedFiles no</td>
    </tr>
    
    
    <tr>
    <td class="org-left">dfiles checkout (Solve conflicts)</td>
    </tr>
    </tbody>
    </table>

