Description des exigences non fonctionnelles du futur système ==============================================================1) Intégration de l'existant Nous devons communiquer avec les exploitants qui s'occupent de l'entretien des stations. Il s'agit donc d'optimiser leurs interventions en rationnalisant la surveillance.2) Robustesse Les stations doit être protégées correctement pour supporter des conditions climatiques extrêmes dans certaines régions. Le système embarqué doit pouvoir revenir à un état stable en cas de reprise.3) Fiabilité On doit éviter toute intervention humaine vis à vis du système. Il doit disposer de mécanismes garantissant leur fonctionnement en continu.4) Evolutivité et maintenabilité Le système peut être amené à évoluer au niveau dimentionnel, fonctionnel et matériel. Il faut donc veiller à l'organiser en sous-systèmes, au comportement normalisé, et qui pourront donc être ajouté, modifiés, ou retiré par la suite sans impacter le système global. Il faut définir les couches lors du développement de l'application pour faire en sorte que le système soit le plus indépendant possible du matériel. 5) Limitations technologiques Le système repose sur certaines technologies dont nous ne maîtrisons pas le fonctionnement (par exemple, le GSM). Il faut donc considérer la différence entre les technologies internes et externes.6) Généricité Notre système doit être conçu à pouvoir décliner à moindre coût pour d'autre applications de type surveillance. Les applications sont nombreuses, mais le fonctionnement global est souvent proche. L'organisation de notre solution doit donc faire abstraction du domaine d'application. Nous pouvons prévenir certains modules changeables.7) Réutilisation Les techniques emplyées ne sont pas fondamentalement nouvelles, nous pouvons donc en profiter pour réutiliser des composants qui ont fait leur preuve. Symétriquement, il faut que les composants de notre propre système puissent être réutilisés à leur tour.8) Ergonomie Le système s'adresse à des non informaticiens, il faut donc que l'interface s'adapte à l'utilisateur et que ce soit facile et convivial pour exploiter le système. Le besoin d'apprentissage doit être minimisé. Il faut aussi assurer la qualité de l'interface sur un appareil portable de type PDA, afin de faciliter son utilisation sur le terrain.9) Traçabilité Le serveur central, qui est en communication avec l'ensemble du système, doit garder une trace de toutes les informations qui transitent et les états de fonctionnement de chaque station. Du côté des stations, les systèmes embarqués doivent également assurer une traçabilité indépendante du serveur en cas de communications impossible ou d'erreurs graves."scale"; value: u'50%')

=======
Description des exigences non fonctionnelles du futur systÃ¨me 
==============================================================
1) IntÃ©gration de l'existant 
Nous devons communiquer avec les exploitants qui s'occupent de l'entretien des stations. Il s'agit donc d'optimiser leurs interventions en rationnalisant la surveillance.

2) Robustesse 
Les stations doit Ãªtre protÃ©gÃ©es correctement pour supporter des conditions climatiques extrÃªmes dans certaines rÃ©gions. Le systÃ¨me embarquÃ© doit pouvoir revenir Ã  un Ã©tat stable en cas de reprise.

3) FiabilitÃ© 
On doit Ã©viter toute intervention humaine vis Ã  vis du systÃ¨me. Il doit disposer de mÃ©canismes garantissant leur fonctionnement en continu.

4) Ã‰volutivitÃ© et maintenabilitÃ© 
Le systÃ¨me peut Ãªtre amenÃ© Ã  Ã©voluer au niveau dimensionnel, fonctionnel et matÃ©riel. Il faut donc veiller Ã  l'organiser en sous-systÃ¨mes, au comportement normalisÃ©, et qui pourront donc Ãªtre ajoutÃ©, modifiÃ©s, ou retirÃ© par la suite sans impacter le systÃ¨me global. Il faut dÃ©finir les couches lors du dÃ©veloppement de l'application pour faire en sorte que le systÃ¨me soit le plus indÃ©pendant possible du matÃ©riel. 

5) Limitations technologiques 
Le systÃ¨me repose sur certaines technologies dont nous ne maÃ®trisons pas le fonctionnement (par exemple, le GSM). Il faut donc considÃ©rer la diffÃ©rence entre les technologies internes et externes.

6) GÃ©nÃ©ricitÃ© 
Notre systÃ¨me doit Ãªtre conÃ§u Ã  pouvoir dÃ©cliner Ã  moindre coÃ»t pour d'autre applications de type surveillance. Les applications sont nombreuses, mais le fonctionnement global est souvent proche. L'organisation de notre solution doit donc faire abstraction du domaine d'application. Nous pouvons prÃ©venir certains modules changeables.

7) RÃ©utilisation 
Les techniques employÃ©es ne sont pas fondamentalement nouvelles, nous pouvons donc en profiter pour rÃ©utiliser des composants qui ont fait leur preuve. SymÃ©triquement, il faut que les composants de notre propre systÃ¨me puissent Ãªtre rÃ©utilisÃ©s Ã  leur tour.

8) Ergonomie 
Le systÃ¨me s'adresse Ã  des non informaticiens, il faut donc que l'interface s'adapte Ã  l'utilisateur et que ce soit facile et convivial pour exploiter le systÃ¨me. Le besoin d'apprentissage doit Ãªtre minimisÃ©. Il faut aussi assurer la qualitÃ© de l'interface sur un appareil portable de type PDA, afin de faciliter son utilisation sur le terrain.

9) TraÃ§abilitÃ© 
Le serveur central, qui est en communication avec l'ensemble du systÃ¨me, doit garder une trace de toutes les informations qui transitent et les Ã©tats de fonctionnement de chaque station. Du cÃ´tÃ© des stations, les systÃ¨mes embarquÃ©s doivent Ã©galement assurer une traÃ§abilitÃ© indÃ©pendante du serveur en cas de communications impossible ou d'erreurs graves.
