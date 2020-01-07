# Sections in a Lexical Entry
(Understanding the hierarchical structure of an entry)

MDF has two built-in hierarchical structures that should be flexible enough to meet most needs. (See "Alternate_Hierarchy" for a discussion of MDF's other hierarchy.) The field codes that mark the boundaries to lexical subsections are \lx, \ps (\pn), \sn, \se. Each of these sections or subsections can take a full set of field markers (except \lc and  \hm, which should only occur at the top of the record).

## Multiple parts of speech
Multiple parts of speech (\ps) are used to organize sections within an entry. A lexeme that fills more than one syntactic slot (as a noun, verb, etc.) should not be handled as homonyms. This is because the different syntactic functions (e.g. 'shower' (n) 'shower' (v) are still clearly related to each other in meaning.
```
\lx shower
 \ps n
 \de a light rain
 \ps vt
 \de to bestow special things on someone
```
MDF's standard printing function starts new \ps fields within an entry on a new line, preceded by an em dash to show that the lexeme form has not changed but its function has.
```
shower   n. a light rain.
       --  vt. to bestow special things on someone.
```

## Multiple Senses
MDF allows sense numbers (\sn) to be used as another level of hierarchy within an entry. In the standard hierarchy, the sense number is lower than part of speech, and so multiple senses should be grouped under the relevant parts of speech to denote related but distinct meanings within a particular part of speech. (See "Alternate_Hierarchy" for a discussion of MDF's other hierarchy.) Multiple senses in each separate part of speech should start with '1' (as seen in the following, more complete entry for 'shower'):
```
\lx shower
 \ps n
 \sn 1
 \de a light rain
 \sn 2
 \de a man-made device for dispensing water in droplets
     on a person; used for bathing
 \sn 3
 \de an event in which gifts are given to someone; 
     as in baby showers and wedding showers

 \ps v
 \sn 1
 \de raining lightly
 \sn 2
 \de to bathe using a device which causes water to
     dispense in droplets on a persons head; usually
     done standing up
 \sn 3
 \de to bestow special things on someone
```

This complex record would print as:
```
shower   n. 1)  a light  rain. 2)  a man-made  device for
         dispensing water  in droplets  on a person; used
         for bathing.  3) an  event in  which  gifts  are
         given to someone; as in baby showers and wedding
         showers.
     --  v. 1)  raining lightly.  2) to  bathe using  a
         device  which   causes  water   to  dispense  in
         droplets  on   a  persons   head;  usually  done
         standing up.  3) to  bestow  special  things  on
         someone.
```

Some lexicographers want to make fine distinctions between subsenses. These can be handled in MDF in the  \sn field with a, b, c, etc. subcategorization.
```
 \lx lexeme
 \ps n
 \sn 1a
 \ge gloss
 \de definition
 \sn 1b
 \ge gloss
 \de definition
 \sn 1c
 \ge gloss
 \de definition

 \sn 2
 \ge gloss
 \de definition

 \sn 3
 \ge gloss
 \de definition
```

Which would have the general printed structure of:
```
lexeme   n. 1a) definition. 1b) definition. 1c) definition.
               2) definition. 3) definition.
```

## Using Subentries
Subentries (\se) provide a further level of hierarchy. These are commonly built around polymorphemic forms in a root-based dictionary (see the MDF field manual (Coward and Grimes, 1995) for an extended discussion).
```
 \lx bren
 \ps vi
 \ge play
 \ee Implies lack of focus or purpose.

 \se brenak
 \ps vt
 \ge play_s.t.
 \de play a game, or play with s.t.

 \se inabren
 \ps n
 \ge recreation ; entertainment

 \se rabrenak
 \ps n
 \ge toy
 \dt 17/Jun/92
```

This would print like the following:
```
bren     vi. play. Implies lack of focus or purpose.
     brenak    vt. play a game, or play with s.t.
     inabren    n. recreation, entertainment.
     rabrenak n. toy.
```
A more complete example using subentries:
```
 \lx bersih
 \ps adj
 \sn 1
 \ge clean
 \de be clean, not dirty or messy
 \sn 2
 \ge innocent
 \de be innocent, without fault

 \se kebersihan
 \ps n
 \ge cleanliness

 \se membersihkan
 \ps vt
 \sn 1
 \ge clean_up
 \de clean s.t. up
 \sn 2
 \ge purify
 \de purify, repent or renounce immoral actions

 \se pembersih
 \ps n
 \sn 1
 \ge cleanser
 \sn 2
 \ge janitor
 \dt 17/Jun/92
```
Which would print as:
```
bersih adj. 1) be clean, not dirty or messy. 2) be innocent, 
           without fault.
    kebersihan n. cleanliness.
    membersihkan vt. 1) clean s.t. up. 2) purify, repent or
           renounce immoral actions.
    pembersih n. 1) cleanser. 2) janitor.
```

