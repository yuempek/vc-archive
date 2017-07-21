<img height="14" width="14" src="resources/icon5.png"/><em>Visual C++ Redistributable</em> Archive &nbsp; <a href="https://paypal.me/e1adkarak0"><img src="https://www.paypalobjects.com/webstatic/mktg/Logo/pp-logo-100px.png"></a>

<ul>
<li><img height="14" width="14" src="resources/icon6.png"/> <em>All In Once Place</em>, you don't need to look for the dependencies in Google and deal with downloading older versions from Microsoft, ever again.</li>
<li><img height="14" width="14" src="resources/icon6.png"/> <em>Flat Packages</em>, meaning the setups are not closed and compressed, and you can browse the structure even before you've instealled anything, or simply copy the files, without the need to install and scrape/look for all of the files in your computer.</li>
<li><img height="14" width="14" src="resources/icon6.png"/> <em>Faster To Install</em>, since I've stripped all the $hit wrapping around the files, but kept the archive fully functional, there is no "uncompression to temporary folder" payload.</li>
<li><img height="14" width="14" src="resources/icon6.png"/> <em>No More Looking In Microsoft For Downloads + Older Archives</em>, you can find most of the VC versions for the x86/x64/arm architectures, even ones that are no longer available or replaced by other versions <br/>and it is super easy to locate it. Plus, there is no longer the "what VC version is 20xx" means, each archive-includes both the official "VC-version", <br/>the full version, and the visual-studio match-year</li>
</ul>

<hr/>
<br/>

Download/Usage

Files are located at <a href="archives/">archives/</a>.

Setup packages (<img height="14" width="14" src="resources/icon_setup.png"/>&nbsp;old setups, newer single-archive <img height="14" width="14" src="resources/icon_msi.png"/>&nbsp;MSI and <img height="14" width="14" src="resources/icon_wix.png"/>&nbsp;Wix) were flattened as much as possible, and compressed with <img height="14" width="14" src="resources/icon_7z.png"/>&nbsp;7zip, <em>for storage sake..</em>.

Once you'll download your desired version of VC,
use 7zip to extract the content into an empty folder,
you may run <img height="14" width="14" src="resources/icon_msi.png"/>&nbsp;MSI,
which is essentially a "copy-to.." script.

Since all the files are located in the same folder,
and do not required any extraction to temporary folder,
the installation itself will finish after few seconds.

If you've noticed that some VC-archives may have, in additional to the <img height="14" width="14" src="resources/icon_msi.png"/>&nbsp;MSI installer, also, a classic <img height="14" width="14" src="resources/icon_installer1.png"/>&nbsp;<code>install.exe</code> file or <img height="14" width="14" src="resources/icon_installer2.png"/>&nbsp;<code>setup.exe</code> file, running those instead of the <img height="14" width="14" src="resources/icon_msi.png"/>&nbsp;MSI one, <strong>should</strong> give you the same end result, installing the <em>VC runtime dlls</em> on your PC, but with the "additional value" of some nice UI, and maybe minimum-requirements pre-check, so if you want to avoid those, stick with the <img height="14" width="14" src="resources/icon_msi.png"/>&nbsp;MSI file.

You don't have to install anything, on most of the packages you can simply grab the VC DLLs, and copy them to the same folder of your application, this is probably a more easy way to distribute an application along with the VC dependencies it needs.

Don't forget to have your application the required manifest (either side-by-side or embedded as <em>resource-24</em>)
read more about VC dependencies, for manifests in here: <a href="http://icompile.eladkarako.com/schema-manifest-for-your-exe"><em>iCompile - </em>Schema-Manifest For Your EXE</a>.

<hr/>

How To Flatten Setup Packages: 
Extracting cab/cab exe installers is simple, just use 7zip.
Extracting MSI single-file archive into a folder, that still has the MSI script, so you could run it to install it, can be done using: <code>msiexec.exe /a archive.msi /qb /l log.txt TARGETDIR="C:\...target-dir...\"</code>.
Extracting <code>Windows Installer XML</code> (<em>WiX</em>), is possible with <a href="https://github.com/wixtoolset/wix3/releases/">wix-toolset</a>'s <code>dark.exe</code>: <code>dark.exe myinstaller.exe -x "C:\...target-dir...\"</code>, and repeating the MSI extract for each of the MSI-archives found under <code>AttachedContainer/packages</code>.

<hr/>

Notes: 
latest VC versions comes with has a folder named "patches" including .MSU files. You may run them if you like to. You can use 7zip to extract them if you like to. <em>I would not mess with it...</em>.

latest VC versions also split the dependencies to <code>runtime_minimal</code> and <code>runtime_additional</code>you can install/copy both or just the minimal- the added value is usually an additional language-sets.

everything in-here is original, as in umodified, even creation/modification dates are the original ones, I've simply stripped-away some of the external-wrappings :]

vc15(2017) is really just a fancy vc14(2015) update (not upgrade!), just like SP1... when installed over it usually replaces the vc14 dlls. it is perfectly fine - vc15 and vc14 are 100% compatible and you can use one in another (module/binary..), if you are unsure just keep both's dll files.

<hr/>

Keywords: <code>vcredist,vcredist_x86,vcredist_x64,x86,x32,64,Wix,extract,MSI,CAB,C Runtime,CRT,Standard C++,MFC,C++ AMP,OpenMP,Microsoft Visual C++ Redistributable 2015,Microsoft Visual C++ Redistributable 2013,Microsoft Visual C++ Redistributable 2012,Microsoft Visual C++ Redistributable 2010,Microsoft Visual C++ Redistributable 2008,Microsoft Visual C++ Redistributable 2005,32-bit,64-bit,Standalone Offline Installer,ddl,download,binary,system</code>.

<br/>

<strong><em>If you've found it useful, and it saved you time and money, consider a small donation <a href="https://paypal.me/e1adkarak0"><img src="https://www.paypalobjects.com/webstatic/mktg/Logo/pp-logo-100px.png"></a> as small token of appreciation, for the amount of time and effort I've put into this project, plus you'll get a free t-shirt too :]</em></strong>
