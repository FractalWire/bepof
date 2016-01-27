# BÉPOF

Custom keyboard layout for X.Org Server.
This layout is derived from the BÉPO French layout.

The changes are meant to ease programing and give a better access to the symbols use in various programing language.

The far right characters in bépo configuration (w, k, z), usefull in english, are move to the right for better access.

Direct accentuated characters (à, ù, è, ê,…) and ç are thrown away (except for é), but still accessible with «dead» characters (`e = è).

Finally, because I'm a VIM user, and because it's quite hard to use this beautifull software without hardcore tweaking with bépo configuration, it is possible to access h, j, k, l keys with a AltGr.

Also, there's a new AltGr key on the left of the keyboard and it is possible to lock AltGr by pressing simultaneously Maj+AltGr.


 ┌─────┐
 │ S A │   S = Shift | Maj,   A = AltGr + Shift | AltGr + Maj
 │ s a │   s = normal,        a = AltGr
 └─────┘

 ┌─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┲━━━━━━━━━┓
 │ # ¶ │ 1 „ │ 2 “ │ 3 ” │ 4   │ 5   │ 6   │ 7 ¬ │ 8 ¼ │ 9 ½ │ 0 ¾ │ ° ′ │ $ ″ ┃ ⌫ Retour┃
 │ ~ ^ │ " — │ ' « │ ` » │ < ≤ │ > ≥ │ @ @ │ + ± │ - − │ / ÷ │ * × │ = ≠ │ % ‰ ┃  arrière┃
 ┢━━━━━┷━┱───┴─┬───┴─┬───┴─┬───┴─┬───┴─┬───┴─┬───┴─┬───┴─┬───┴─┬───┴─┬───┴─┬───┺━┳━━━━━━━┫
 ┃       ┃ B ¦ │ É § │ P   │ O Œ │ F ` │ \   │ V   │ D Ð │ L   │ J Ĳ │ [   │ ]   ┃Entrée ┃
 ┃Tab ↹  ┃ b | │ é & │ p   │ o œ │ f ~ │ /   │ v ˇ │ d ð │ l / │ j ĳ │ ( { │ ) } ┃   ⏎   ┃
 ┣━━━━━━━┻┱────┴┬────┴┬────┴┬────┴┬────┴┬────┴┬────┴┬────┴┬────┴┬────┴┬────┴┬────┺┓      ┃
 ┃        ┃ A Æ │ U   │ I ˙ │ E ¤ │ ; ̛  │ C ſ │ T H │ S J │ R K │ N L │ ? ¿ │ ! ¡ ┃      ┃
 ┃Maj ⇬   ┃ a æ │ u   │ i ¨ │ e € │ , ’ │ c © │ t h │ s j │ r k │ n l │ . … │ : ˛ ┃      ┃
 ┣━━━━━━━┳┹────┬┴────┬┴────┬┴────┬┴────┬┴────┬┴────┬┴────┬┴────┬┴────┬┴────┲┷━━━━━┻━━━━━━┫
 ┃       ┃Alt  │ W , │ Y Þ │ X ™ │ K ẞ │ Z Ə │ ^ ˝ │ Q ̣  │ G   │ H ‡ │ M ª ┃             ┃
 ┃Shift ⇧┃Gr ⇮ │ w ¸ │ y þ │ x ® │ k ß │ z ə │ ` ´ │ q ˚ │ g µ │ h † │ m º ┃Shift ⇧      ┃
 ┣━━━━━━━╋━━━━━┷━┳━━━┷━━━┱─┴─────┴─────┴─────┴─────┴─────┴───┲━┷━━━━━╈━━━━━┻━┳━━━━━━━┳━━━┛
 ┃       ┃       ┃       ┃ Espace inséc.   Espace inséc. fin ┃       ┃       ┃       ┃
 ┃Ctrl   ┃Meta   ┃Alt    ┃ ␣ (Espace)      _               ␣ ┃AltGr ⇮┃Menu   ┃Ctrl   ┃
 ┗━━━━━━━┻━━━━━━━┻━━━━━━━┹───────────────────────────────────┺━━━━━━━┻━━━━━━━┻━━━━━━━┛


## Installation

You'd have to modify several file for it to work :

  * /usr/share/X11/xkb/rules/\*.lst, add this line near "bepo" : "bepof     fr: French (Bepo, ergonomic, Dvorak way, customized)"
  * /usr/share/X11/xkb/rules/base.xml, add these lines near "bepo" variant : 
        <variant>
          <configItem>
            <name>bepof</name>
            <description>French (Bepo, ergonomic, Dvorak way, customized)</description>
          </configItem>
        </variant>
  * /usr/share/X11/xkb/symbols/fr append the file bepof to it, for exemple by issuing this command : `cat bepof >> /usr/share/X11/xkb/symbols/fr`. You will probably need root privilege for this.

You can now use the command `setxkbmap -layout fr -variant bepof` to test it out. If you want this change to be permanent, you should edit the /etc/X11/xorg.conf.d folder. Refer to online documentation for more details.


## What next ?

This is the 0.1 version of the keyboard. There might be some changes in the future. In particular, a better use of the AltGr keys : some of them are simply blank which is not optimal…

I also wonder if I should swap o <-> f keys so that 'of' or 'fo' combination are not on the left index only… 