Exigences de sécurité de l’application des notes

#	Exigence	Vérification	Étape du SDLC	Test
S1	Le système doit empêcher les injections SQL lors de la recherche des notes.	Vérifier que les entrées utilisateur ne permettent pas de modifier une requête SQL.	Développement	test_recherche_resiste_a_l_injection
S2	Le système doit refuser la modification d’une note sans authentification.	Vérifier la présence d’un jeton valide dans la requête.	Développement et tests	test_modification_refusee_sans_identification
S3	Le système doit empêcher un étudiant de modifier une note.	Vérifier le rôle de l’utilisateur connecté.	Développement et tests	test_modification_refusee_a_un_etudiant
S4	Le système doit empêcher un enseignant de modifier les notes d’un autre module.	Vérifier que le module de l’enseignant correspond au module de la note.	Développement et tests	test_modification_refusee_a_un_autre_module
S5	Le système doit accepter uniquement les notes numériques comprises entre 0 et 20.	Vérifier que la note est un nombre valide compris entre 0 et 20.	Développement et tests	test_note_invalide_refusee
S6	Le système doit autoriser un enseignant à modifier la note d’un étudiant de son module.	Vérifier le rôle de l’enseignant et son autorisation sur le module.	Tests	test_modification_par_l_enseignant_du_module
S7	Le système doit afficher un message d’erreur sans révéler de détails techniques.	Vérifier que les erreurs ne divulguent pas d’informations techniques.	Tests et maintenance	test_erreur_sans_detail_technique