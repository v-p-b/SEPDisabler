Symantec Endpoint Protection Disabler (from 2018)
=================================================

Someone asked about similar techniques on [Reddit](https://www.reddit.com/r/redteamsec/comments/18p044i/any_tricks_for_disabling_sep_cybereason/) and it reminded that I never released this one.

The main idea is this:

* Register COM servers under your own HKCU tree
* Execute the SEP GUI that is usually accessible for all users but with limited functionality
* Trigger the COM server loading so your DLL gets loaded into the GUI
* Since access checks for many features are implemented in your current process, you can for example just patch the "Am I a local admin?" API calls and unlock features. The "server" process will happily accept any config changes requested by its trusted GUI counterpart. 

I couldn't find my original sources, some disassembly required :) (and again, this worked in 2018, a lot may have changed since then).

[Demo](https://youtu.be/sQ49cNMz3HU)
