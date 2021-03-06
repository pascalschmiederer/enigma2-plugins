AC_INIT([enigma2-plugins],[4.2.0],[enigma2-devel@lists.elitedvb.net])
AM_INIT_AUTOMAKE([dist-bzip2 foreign no-define tar-pax])
AC_CONFIG_HEADERS([enigma2-plugins-config.h])

# Silent rules are available since 1.11, but older versions
# are still in use. So don't use them unconditionally.
m4_ifdef([AM_SILENT_RULES], [AM_SILENT_RULES([yes])])

AC_USE_SYSTEM_EXTENSIONS
AC_SYS_LARGEFILE

AC_PROG_CC
AC_PROG_CXX
m4_ifdef([LT_INIT], [LT_INIT], [AC_PROG_LIBTOOL])
AC_CONFIG_MACRO_DIR([m4])

AC_PATH_PROG(MSGFMT, msgfmt, AC_MSG_ERROR(Could not find msgfmt))

AM_PATH_PYTHON
AX_PYTHON_DEVEL
AX_PTHREAD

PKG_CHECK_MODULES(ENIGMA2, enigma2)
PKG_CHECK_MODULES(GSTREAMER, gstreamer-1.0 gstreamer-pbutils-1.0)
PKG_CHECK_MODULES(LIBCRYPTO, libcrypto)
PKG_CHECK_MODULES(LIBTIRPC, libtirpc)

AC_ARG_WITH(debug,
	AS_HELP_STRING([--without-debug],[disable debugging code]),
	[with_debug="$withval"],[with_debug="yes"])
if test "$with_debug" = "yes"; then
	DEBUG_CFLAGS="-ggdb3"
	AC_DEFINE([DEBUG],[1],[Define to 1 to enable debugging code])
fi
AC_SUBST(DEBUG_CFLAGS)

AC_ARG_WITH(po,
	AS_HELP_STRING([--with-po],[enable updating of po files]),
	[with_po="$withval"],[with_po="no"])
if test "$with_po" = "yes"; then
	AC_PATH_PROG(MSGINIT, msginit)
	AC_PATH_PROG(MSGMERGE, msgmerge)
	AC_PATH_PROG(MSGUNIQ, msguniq)
	AC_PATH_PROG(XGETTEXT, xgettext)
	if test -z "$MSGINIT" -o -z "$MSGMERGE" -o -z "$MSGUNIQ" -o -z "$XGETTEXT"; then
		AC_MSG_ERROR([Could not find required gettext tools])
	fi
fi
AM_CONDITIONAL(UPDATE_PO, test "$with_po" = "yes")

AC_CONFIG_FILES([
Makefile

3dsettings/Makefile
3dsettings/meta/Makefile
3dsettings/src/Makefile

aihdcontroler/Makefile
aihdcontroler/meta/Makefile
aihdcontroler/src/Makefile
aihdcontroler/src/comp/Makefile
aihdcontroler/src/data/Makefile

antiscrollbar/Makefile
antiscrollbar/meta/Makefile
antiscrollbar/src/Makefile

aspectratioswitch/Makefile
aspectratioswitch/meta/Makefile
aspectratioswitch/src/Makefile

audiorestart/Makefile
audiorestart/img/Makefile
audiorestart/meta/Makefile
audiorestart/src/Makefile

audiosync/Makefile
audiosync/img/Makefile
audiosync/meta/Makefile
audiosync/src/Makefile

automaticcleanup/Makefile
automaticcleanup/meta/Makefile
automaticcleanup/src/Makefile

automatictimerlistcleanup/Makefile
automatictimerlistcleanup/meta/Makefile
automatictimerlistcleanup/src/Makefile

automaticvolumeadjustment/Makefile
automaticvolumeadjustment/meta/Makefile
automaticvolumeadjustment/src/Makefile

autoresolution/Makefile
autoresolution/meta/Makefile
autoresolution/src/Makefile

autotimer/Makefile
autotimer/meta/Makefile
autotimer/src/Makefile
autotimer/src/WebChilds/Makefile
autotimer/src/WebComponents/Makefile
autotimer/src/WebComponents/Sources/Makefile
autotimer/src/WebScreens/Makefile
autotimer/src/web/Makefile
autotimer/src/web-data/Makefile

babelzapper/Makefile
babelzapper/etc/Makefile
babelzapper/meta/Makefile
babelzapper/src/Makefile

birthdayreminder/Makefile
birthdayreminder/meta/Makefile
birthdayreminder/src/Makefile

bitrateviewer/Makefile
bitrateviewer/meta/Makefile
bitrateviewer/src/Makefile
bitrateviewer/src/bitratecalc/Makefile

bonjour/Makefile
bonjour/meta/Makefile
bonjour/src/Makefile

cdinfo/Makefile
cdinfo/meta/Makefile
cdinfo/src/Makefile

channelselectionshorttitle/Makefile
channelselectionshorttitle/src/Makefile

curlytx/Makefile
curlytx/meta/Makefile
curlytx/src/Makefile

dreamexplorer/Makefile
dreamexplorer/meta/Makefile
dreamexplorer/src/Makefile
dreamexplorer/src/res/Makefile

dreamirc/Makefile
dreamirc/meta/Makefile
dreamirc/src/Makefile
dreamirc/src/protocols/Makefile

dreammediathek/Makefile
dreammediathek/src/Makefile

dvdbackup/Makefile
dvdbackup/meta/Makefile
dvdbackup/src/Makefile

dyndns/Makefile
dyndns/src/Makefile
dyndns/meta/Makefile

easyinfo/Makefile
easyinfo/meta/Makefile
easyinfo/src/Makefile

easymedia/Makefile
easymedia/meta/Makefile
easymedia/src/Makefile

ecasa/Makefile
ecasa/meta/Makefile
ecasa/src/Makefile

eibox/Makefile
eibox/meta/Makefile
eibox/src/Makefile
eibox/src/images/Makefile

elektro/Makefile
elektro/meta/Makefile
elektro/src/Makefile

emailclient/Makefile
emailclient/meta/Makefile
emailclient/src/Makefile

emission/Makefile
emission/meta/Makefile
emission/src/Makefile

eparted/Makefile
eparted/meta/Makefile
eparted/src/Makefile

epgcopy/Makefile
epgcopy/meta/Makefile
epgcopy/src/Makefile

epgrefresh/Makefile
epgrefresh/meta/Makefile
epgrefresh/src/Makefile
epgrefresh/src/localehelp/Makefile
epgrefresh/src/webinterface/Makefile

epgsearch/Makefile
epgsearch/meta/Makefile
epgsearch/src/Makefile

eurotictv/Makefile
eurotictv/meta/Makefile
eurotictv/src/Makefile

eventlist/Makefile
eventlist/src/Makefile

eventposition/Makefile
eventposition/src/Makefile

fancontrol2/Makefile
fancontrol2/meta/Makefile
fancontrol2/src/Makefile
fancontrol2/src/data/Makefile

filebrowser/Makefile
filebrowser/meta/Makefile
filebrowser/src/Makefile

fritzcall/Makefile
fritzcall/meta/Makefile
fritzcall/src/Makefile
fritzcall/src/images/Makefile
fritzcall/src/images/MODERN/Makefile 

fstabeditor/Makefile
fstabeditor/meta/Makefile
fstabeditor/src/Makefile

ftpbrowser/Makefile
ftpbrowser/meta/Makefile
ftpbrowser/src/Makefile
ftpbrowser/src/images/Makefile

genuinedreambox/Makefile
genuinedreambox/meta/Makefile
genuinedreambox/src/Makefile

googlemaps/Makefile
googlemaps/meta/Makefile
googlemaps/src/Makefile

growlee/Makefile
growlee/meta/Makefile
growlee/src/Makefile

imdb/Makefile
imdb/meta/Makefile
imdb/src/Makefile

infobartunerstate/Makefile
infobartunerstate/meta/Makefile
infobartunerstate/src/Makefile
infobartunerstate/src/Handler/Makefile

internetradio/Makefile
internetradio/meta/Makefile
internetradio/src/Makefile
internetradio/src/images/Makefile
internetradio/src/WebComponents/Makefile
internetradio/src/WebComponents/Sources/Makefile
internetradio/src/WebScreens/Makefile
internetradio/src/web/Makefile
internetradio/src/web-data/Makefile
internetradio/src/web-data/img/Makefile
internetradio/src/web-data/tpl/Makefile

kiddytimer/Makefile
kiddytimer/img/Makefile
kiddytimer/meta/Makefile
kiddytimer/src/Makefile

letterbox/Makefile
letterbox/src/Makefile
letterbox/meta/Makefile

logomanager/Makefile
logomanager/logodir_hdd/Makefile
logomanager/meta/Makefile
logomanager/src/Makefile

mediadownloader/Makefile
mediadownloader/meta/Makefile
mediadownloader/src/Makefile

menusort/Makefile
menusort/meta/Makefile
menusort/src/Makefile

merlinepg/Makefile
merlinepg/meta/Makefile
merlinepg/src/Makefile

merlinepgcenter/Makefile
merlinepgcenter/meta/Makefile
merlinepgcenter/src/Makefile
merlinepgcenter/skins/Makefile
merlinepgcenter/images/Makefile
merlinepgcenter/images/FHD/Makefile
merlinepgcenter/images/HD/Makefile
merlinepgcenter/images/HD_BORDER/Makefile
merlinepgcenter/images/SD/Makefile
merlinepgcenter/images/XD/Makefile
merlinepgcenter/images/XD_BORDER/Makefile
merlinepgcenter/images/HD_Elgato/Makefile

merlinmusicplayer/Makefile
merlinmusicplayer/meta/Makefile
merlinmusicplayer/src/Makefile
merlinmusicplayer/src/images/Makefile
merlinmusicplayer/src/merlinmp3player/Makefile

meteoitalia/Makefile
meteoitalia/meta/Makefile
meteoitalia/src/Makefile

mosaic/Makefile
mosaic/meta/Makefile
mosaic/src/Makefile

moviecut/Makefile
moviecut/meta/Makefile
moviecut/src_cc/Makefile
moviecut/src_py/Makefile

movielistpreview/Makefile
movielistpreview/meta/Makefile
movielistpreview/src/Makefile

movieretitle/Makefile
movieretitle/meta/Makefile
movieretitle/src/Makefile

moviesearch/Makefile
moviesearch/meta/Makefile
moviesearch/src/Makefile

movieselectionquickbutton/Makefile
movieselectionquickbutton/meta/Makefile
movieselectionquickbutton/src/Makefile

movietagger/Makefile
movietagger/etc/Makefile
movietagger/meta/Makefile
movietagger/src/Makefile

movieepg/Makefile
movieepg/meta/Makefile
movieepg/src/Makefile

mphelp/Makefile
mphelp/meta/Makefile
mphelp/src/Makefile

multirc/Makefile
multirc/src/Makefile
multirc/meta/Makefile

mytube/Makefile
mytube/meta/Makefile
mytube/src/Makefile

namezap/Makefile
namezap/meta/Makefile
namezap/src/Makefile

netcaster/Makefile
netcaster/meta/Makefile
netcaster/src/Makefile
netcaster/src/bin/Makefile
netcaster/src/bin/interface/Makefile
netcaster/src/etc/Makefile

networkbrowser/Makefile
networkbrowser/meta/Makefile
networkbrowser/src/Makefile
networkbrowser/src/icons/Makefile
networkbrowser/src/lib/Makefile

ncidclient/Makefile
ncidclient/meta/Makefile
ncidclient/src/Makefile

ofdb/Makefile
ofdb/meta/Makefile
ofdb/src/Makefile

orfteletext/Makefile
orfteletext/meta/Makefile
orfteletext/src/Makefile

partnerbox/Makefile
partnerbox/meta/Makefile
partnerbox/src/Makefile
partnerbox/src/icons/Makefile
partnerbox/src/servicewebts/Makefile

permanentclock/Makefile
permanentclock/meta/Makefile
permanentclock/src/Makefile

permanenttimeshift/Makefile
permanenttimeshift/meta/Makefile
permanenttimeshift/images/Makefile
permanenttimeshift/src/Makefile
permanenttimeshift/src/eitsave/Makefile
permanenttimeshift/src/createapscfiles/Makefile

pipservicerelation/Makefile
pipservicerelation/src/Makefile
pipservicerelation/meta/Makefile

pipzap/Makefile
pipzap/meta/Makefile
pipzap/src/Makefile

pluginhider/Makefile
pluginhider/meta/Makefile
pluginhider/src/Makefile

pluginsort/Makefile
pluginsort/meta/Makefile
pluginsort/src/Makefile

podcast/Makefile
podcast/etc/Makefile
podcast/meta/Makefile
podcast/src/Makefile

pushservice/Makefile
pushservice/etc/Makefile
pushservice/meta/Makefile
pushservice/src/Makefile
pushservice/src/Controller/Makefile
pushservice/src/Services/Makefile
pushservice/src/Services/gntp/Makefile
pushservice/src/Services/mail/Makefile

quickbutton/Makefile
quickbutton/meta/Makefile
quickbutton/src/Makefile

reconstructapsc/Makefile
reconstructapsc/meta/Makefile
reconstructapsc/src_cc/Makefile
reconstructapsc/src_py/Makefile

reftopiconname/Makefile
reftopiconname/src/Makefile

remotetimer/Makefile
remotetimer/meta/Makefile
remotetimer/src/Makefile

satipclient/Makefile
satipclient/meta/Makefile
satipclient/src/Makefile

satloader/Makefile
satloader/meta/Makefile
satloader/src/Makefile

seekbar/Makefile
seekbar/meta/Makefile
seekbar/src/Makefile

serienfilm/Makefile
serienfilm/meta/Makefile
serienfilm/src/Makefile
serienfilm/src/icons/Makefile

seriesplugin/Makefile
seriesplugin/etc/Makefile
seriesplugin/meta/Makefile
seriesplugin/src/Makefile
seriesplugin/src/Images/Makefile
seriesplugin/src/Logos/Makefile
seriesplugin/src/Identifiers/Makefile
seriesplugin/src/Skins/Makefile

setpasswd/Makefile
setpasswd/meta/Makefile
setpasswd/src/Makefile

showclock/Makefile
showclock/meta/Makefile
showclock/src/Makefile

simplerss/Makefile
simplerss/meta/Makefile
simplerss/src/Makefile

startupservice/Makefile
startupservice/meta/Makefile
startupservice/src/Makefile

startuptostandby/Makefile
startuptostandby/meta/Makefile
startuptostandby/src/Makefile

subsdownloader2/Makefile
subsdownloader2/meta/Makefile
subsdownloader2/src/Makefile
subsdownloader2/src/pic/Makefile
subsdownloader2/src/pic/buttons/Makefile
subsdownloader2/src/pic/buttons/HD/Makefile
subsdownloader2/src/pic/res/Makefile
subsdownloader2/src/SourceCode/Makefile
subsdownloader2/src/SourceCode/chardet/Makefile
subsdownloader2/src/SourceCode/periscope/Makefile
subsdownloader2/src/SourceCode/periscope/services/Makefile
subsdownloader2/src/SourceCode/periscope/services/BierDopje/Makefile
subsdownloader2/src/SourceCode/periscope/services/OpenSubtitle/Makefile
subsdownloader2/src/SourceCode/periscope/services/Subtitulos/Makefile
subsdownloader2/src/SourceCode/xbmc_subtitles/Makefile
subsdownloader2/src/SourceCode/xbmc_subtitles/services/Makefile
subsdownloader2/src/SourceCode/xbmc_subtitles/services/Itasa/Makefile

svdrp/Makefile
svdrp/meta/Makefile
svdrp/src/Makefile

tageditor/Makefile
tageditor/meta/Makefile
tageditor/src/Makefile

teletext/Makefile
teletext/meta/Makefile
teletext/src/Makefile

trackautoselect/Makefile
trackautoselect/meta/Makefile
trackautoselect/src/Makefile

toolkit/Makefile
toolkit/src/Makefile

tubelib/Makefile
tubelib/meta/Makefile
tubelib/src/Makefile
tubelib/src/youtube/Makefile

tvcharts/Makefile
tvcharts/meta/Makefile
tvcharts/src/Makefile

unwetterinfo/Makefile
unwetterinfo/meta/Makefile
unwetterinfo/src/Makefile

valixdcontrol/Makefile
valixdcontrol/meta/Makefile
valixdcontrol/src/Makefile
valixdcontrol/src/comp/Makefile
valixdcontrol/src/data/Makefile

videocolorspace/Makefile
videocolorspace/meta/Makefile
videocolorspace/src/Makefile

virtualzap/Makefile
virtualzap/meta/Makefile
virtualzap/src/Makefile

vlcplayer/Makefile
vlcplayer/meta/Makefile
vlcplayer/src/Makefile
vlcplayer/src/servicets/Makefile

vps/Makefile
vps/meta/Makefile
vps/src_cc/Makefile
vps/src_py/Makefile
vps/src_py/web/Makefile
vps/src_py/web-data/Makefile
vps/src_py/WebComponents/Makefile
vps/src_py/WebComponents/Sources/Makefile

weatherplugin/Makefile
weatherplugin/meta/Makefile
weatherplugin/src/Makefile
weatherplugin/src/weather_icons/Makefile

weathercomponent/Makefile
weathercomponent/src/Makefile

weathercomponenthandler/Makefile
weathercomponenthandler/src/Makefile


webadmin/Makefile
webadmin/meta/Makefile
webadmin/src/Makefile
webadmin/src/mobile/Makefile
webadmin/src/web/Makefile
webadmin/src/WebChilds/Makefile
webadmin/src/WebComponents/Makefile
webadmin/src/WebComponents/Sources/Makefile
webadmin/src/web-data/Makefile
webadmin/src/web-data/tpl/Makefile
webadmin/src/web-data/img/Makefile
webadmin/src/WebScreens/Makefile

webcamviewer/Makefile
webcamviewer/meta/Makefile
webcamviewer/src/Makefile

webbouqueteditor/Makefile
webbouqueteditor/src/Makefile
webbouqueteditor/meta/Makefile
webbouqueteditor/src/web/Makefile
webbouqueteditor/src/web-data/Makefile
webbouqueteditor/src/WebChilds/Makefile
webbouqueteditor/src/WebComponents/Makefile
webbouqueteditor/src/WebComponents/Sources/Makefile
webbouqueteditor/src/WebScreens/Makefile

webinterface/Makefile
webinterface/meta/Makefile
webinterface/src/Makefile
webinterface/src/m/Makefile
webinterface/src/mobile/Makefile
webinterface/src/web/Makefile
webinterface/src/web-data/Makefile
webinterface/src/web-data/css/Makefile
webinterface/src/web-data/fonts/Makefile
webinterface/src/web-data/gfx/Makefile
webinterface/src/web-data/img/Makefile
webinterface/src/web-data/lib/Makefile
webinterface/src/web-data/lib/lang/Makefile
webinterface/src/web-data/lib/datepicker/Makefile
webinterface/src/web-data/lib/datepicker/media/Makefile
webinterface/src/web-data/m/Makefile
webinterface/src/web-data/m/css/Makefile
webinterface/src/web-data/m/css/themes/Makefile
webinterface/src/web-data/m/css/themes/images/Makefile
webinterface/src/web-data/m/script/Makefile
webinterface/src/web-data/tpl/Makefile
webinterface/src/web-data/tpl/default/Makefile
webinterface/src/web-data/tpl/default/streaminterface/Makefile
webinterface/src/WebChilds/Makefile
webinterface/src/WebChilds/External/Makefile
webinterface/src/WebComponents/Makefile
webinterface/src/WebComponents/Converter/Makefile
webinterface/src/WebComponents/Sources/Makefile

werbezapper/Makefile
werbezapper/meta/Makefile
werbezapper/src/Makefile

yttrailer/Makefile
yttrailer/meta/Makefile
yttrailer/src/Makefile

zaphistorybrowser/Makefile
zaphistorybrowser/meta/Makefile
zaphistorybrowser/src/Makefile

zapstatistic/Makefile
zapstatistic/meta/Makefile
zapstatistic/src/Makefile

po/Makefile
])
AC_OUTPUT
