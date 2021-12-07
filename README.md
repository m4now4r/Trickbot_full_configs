   Trickbot_configs
    +DLL


   https://github.com/hasherezade/malware_analysis

   Decoders for TrickBot's elements

   trick_decoder.py - decodes TrickBot's core modules (32/64-bit bots) - from resources of the TrickBot loader executable (obsolete, works for the          first version of TrickBot)
   trick_config_decoder.py - decodes TrickBot's hardcoded configuration (from the resource) + downloaded modules and their configuration
   rick_settings_decoder.py - decodes BotKey and mcconfig from the settings file (i.e. settings.ini dropped in the TrickBot installation directory)
   make_bot_key.cpp - a keygen for BotKey (must be run on the infected machine). Compiled version: https://goo.gl/7Sf1E1


   The BotKey can be obtained in two ways:

   decoded:
   Use trick_settings_decoder.py and the settings file dropped by TrickBot.
   
   generated:
   Compile make_bot_key.cpp (or download https://goo.gl/7Sf1E1 ) and run it on the same machine, where the encrypted files were dropped.
   
   Then, you can pass the obtained key to trick_config_decoder.py.

   Example:

    ./trick_config_decoder.py --botkey 2E9EA9FE45FDBA4289F494AF959FAB1A828948E19309DD3C80AD4202728821DB --datafile Data/injectDll32
    Decoded: 1390000 bytes
    Dumped decoded to: Data/injectDll32.out
    Extracted Module to: Data/injectDll32.dll
  
   Decoding the BotKey and mcconfig

   Use trick_settings_decoder.py.

   Example:

    /trick_settings_decoder.py --file ~/settings.ini --brute
    
      

    <mcconf>
    <ver>1000499</ver>
    <gtag>tt0002</gtag>
    <servs>
    <srv>5.182.210.226:443</srv>
    <srv>82.146.62.52:443</srv>
    <srv>193.26.217.243:443</srv>
    [...]
    <srv>171.100.142.238:449</srv>
    <srv>186.232.91.240:449</srv>
    <srv>181.196.207.202:449</srv>
    </servs>
    <autorun>
    <module name="pwgrab"/>
    </autorun>
    </mcconf>
