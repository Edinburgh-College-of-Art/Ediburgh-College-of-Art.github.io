>***Background:** This short paper was written in 1999 in fulfillment of
>the 24-hour part of Stanford's Ph.D. “University Special Area Exams” and
>is hence somewhat cursory. It was presented here with minor corrections
>in its original version in an attempt to make it accessible to the
>interested outside the departmental archives. Thus, the code fragments
>given here pertain to the Common Music version current at that time,
>1.3. Please see the links above for updated versions of the code. Also
>note that Rick Taube, the author of Common Music, has meanwhile reworked
>this paper into chapter 22 of his book “Notes from the Meta-Level: An
>Introduction to Computer Composition”, Swets & Zeitlinger (in print).*

An Algorithmic Model of György Ligeti's Étude No. 1, *Désordre* (1985)
======================================================================

Probably inspired by its title, the first of György Ligeti's “Etudes for
Piano” has been analyzed in great depth with respect to a perceived
antagonism between chaos and order in the composition ([Kinzler,
1991](#kinzler-91)). However, while the study does discuss possible
algorithms that Ligeti might have used during the compositional process,
it exhibits a fervent musicological passion for infinitesimally minute
details. As a result, it largely fails to address matters related to the
composition process and thus to explain Ligetis decisions from a
perspective of *algorithmic control*.

The purpose of this paper is to arrive at some idea of what specific
“knobs” the presumedly employed algorithms offered Ligeti and, hence,
what compositorial potential they represent within the structural
framework of the near-finished etude. To accomplish this, the
composition is first analyzed with what is believed to constitute
reasonable neglect of accidental details and then *modeled* in the MIDI
domain using [Common
Music](https://web.archive.org/web/20080220172441/http://commonmusic.sourceforge.net/doc/)
as a score description language. As a model, it does make an honest
attempt to be “realistic,” but also trades off accuracy against
flexibility. After all, there is no point in implementing an algorithm
that cannot be “tossed around” in parameter-space! The presumed
algorithms are then discussed briefly with regard to their historical
background. Following that, hints are given for taking the model for a
spin and generating general *désordre*.


A note regarding score references: since “Désordre” does largely away
with synchronized barlines, references to the score need to be fully
specified with page, system, and measure numbers—and, where necessary,
an indication of the part. In the following, this information will be
given in shorthand notation as

*P*:*S*\[*u*|*l*\].*M*

where *P*, *S*, and *M* denote page, system, and measure number, and—if
necessary—*u* or *l* upper or lower part, respectively. Where systems
begin with partial measures, the first complete measure is counted as
measure 1. All numbers follow the (only) facsimile edition ([Ligeti,
1985](#ligeti-85)).

Structure
---------

### Description

The textural make-up of the etude is comparably straightforward in that
each hand is assigned its own part, and that both parts share a common,
layered substructure and a continuously pulsating eighth-note raster.
Furthermore, each part is restricted to a “mode”—the right hand to
“white” keys and the left hand to “black” keys. As crudely
keyboard-oriented and commonplace as this use of modality may seem, it
actually presents a rather practicable choice that allows Ligeti to let
both technically relatively difficult parts share a register where so
desired.

Aside from these common characteristics, the parts are temporally quite
independent and follow their own processual logic. That is, although
stretches with near-synchronized phrase structures and prominent formal
junctures exist, they are metrically and rhythmically independent when
viewed on sub-formal levels. This temporal independence is central to
the composition in that, on a large scale, most of its form-defining
features emerge from it.

Internally, each part is a combination of continuously rising eighth
note runs in the background and a rhythmically pronounced and slower
melodic line in the foreground. These foreground melodies are played
*forte* throughout the piece and gain further prominence by progressing
in increasingly dense chords—thus in effect establishing themselves as
an autonomous layer against the eight-note background rather than
relating to it as melodies to their accompaniment. Yet, both foreground
lines feature a phrase structure that is reminiscent of traditional
melodic A A' B forms, where two closely related shorter phrases are
followed by a longer and developing third phrase. In addition, the
phrasing hints, despite the distortion that is induced by an
asymmetrical meter in each part, at an underlying simple and song-like
two-beat meter. A similarly asymmetric “meter” that is suggested in both
background layers by eighth-note groups of differing lengths is
relatively negligible compared to the prominent metric structure in the
foreground layers.

On a formal level, finally, the piece is structured by both, the
temporal and pitch space-related behaviour of its two parts. A first
section, 404 eighth notes long, from the beginning of the piece to
3:4.4, is mostly static in tempo, in spite of a small speed-up towards
the end. The following section, which extends for 231 eigth notes until
4:4.7, accelerates the foreground voices until their beat equals an
eighth note. At this point a typical “ligetiesque” cut interrupts the
lower part, which had by then hit the bottom of the piano range, and
resumes with both foreground lines in their original tempo and the lower
part in the discant region, producing an aural effect of sudden
slow-motion. This third section extends for the remaining 429 eigth
notes to the end of the piece and is characterized by a static tempo in
the upper part and a slowing down of the lower part.

### The Data

Both foreground lines consist of cyclic repetitions of a constant step
pattern (see [Figure 1](#step-patterns)). With each cycle, this pattern
is transposed diatonically by a constant interval. The pattern for the
upper part consists of 26 steps, 7 for each of the A phrases and 12 for
phrase B. The pattern for the lower part has 33 steps, again 7 for each
of the A phrases but this time 19 in the extended phrase B.

![step
patterns](http://www.fictive.com/t/pbl/1999_desordre/step-patterns.gif)

**Figure 1:** Upper and lower part foreground step patterns.

> Archive Note: figure missing

Although these patterns bear a strong resemblance to material that has
been generated by a rewrite system—a sequence of “generations” combined
with an overall expanding gesture—they satisfy too many traditional
musical criteria in order not to call for a standard musical
description.

The contours of both patterns are highly similar, and especially the
upper part, which could have easily been generated by a
context-sensitive grammar, exhibits strong motivic features. In contrast
to the lower part's pattern, whose B phrase extends by 2 bars beyond the
expected 8 bars and ends in a “whole” note, however, the upper part's B
phrase falls short by 2 bars and loops instantly back to its beginning.

There are overall 14 cycles in the upper part, each of which is
transposed *diatonically* one step upwards and, due to its greater
length, only 11 cycles in the lower part. The smaller number of
cycles—which translates into fewer transpositions—is overcompensated for
by a two-step diatonic transposition downwards and the fact that the
lower part's pentatonic mode has fewer steps per octave than the
heptatonic mode in the upper part. The cycles align with the score as
follows:

``` {.codefrag}
Cycles:
  Lower Part:               Upper Part:
   #  Transp. Start          #  Transp. Start
  ===================                   ===================
  ---------------------- Section I: -----------------------
   1: ds3     2:1.0              1: b4      2:1.0
                     2: c5      2:2.7
   2: as2     2:3.5
                     3: d5      2:4.7
   3: fs2     3:2.2
                     4: e5      3:2.6
  --------------------- Section II: -----------------------
   4: cs2     3:4.4              5: f5      3:4.4
                     6: g5      3:4.11
   5: gs1     4:1.3
                     7: a5      4:1.7
   6: ds1     4:2.3
                     8: b5      4:2.5
   7: as0     4:3.2
                     9: c6      4:3.3
                    10: d6      4:3.10
   8: fs0     4:4.1 (1)
  --------------------- Section III: -----------------------
              4:4.7             11: e6      4:4.7
   9: cs5     5:1.2
                    12: f6      5:2.4
  10: gs4     5:3.7
                    13: g6      5:4.4
                    14: a6      6:2.4 (2)
  11: ds4     6:2.4 (3)

(1) Cycle 8 in the lower part reaches the bottom of the piano range
  and discontinues after m. 4 in phrase B only to resume immediately in the
  treble clef (4:4.7).  The first note of this continuation should read fs
  but for obvious reasons is given as fs5 to the right hand.
(2) Cycle is cut off after m. 3 in Phrase B.
(3) Cycle is cut off after m. 2 in Phrase A'.

```

The rhythmic picture is less clear due to rasterization effects in the
acceleration and deceleration of the patterns. The sequence of rhythms
in the upper and lower parts read as follows:

```
Rhythms Upper Part:
; ------------------------------; Sect. I Little Disorder       [404 e]
  3 5 3 5 5 3 7         ; cycle 1
  3 5 3 5 5 3 7
  3 5 3 5 5 3 3 4 5 3 3 5
  3 5 3 4 5 3 8         ; cycle 2
  3 5 3 4 5 3 8
  3 5 3 4 5 3 3 5 5 3 3 4
  3 5 3 5 5 3 7         ; cycle 3
  3 5 3 5 5 3 7
  3 5 3 5 5 3 3 4 5 3 3 5
  3 5 3 4 5 2 7         ; cycle 4 -- Speed-Up
  2 4 2 4 4 2 5
  2 3 2 3 3 1 1 3 3 1 1 3
; ------------------------------; Sect. II Rapid Accelerando        [231 e]
  1 2 1 2 2 1 3         ; cycle 5 -- start is in sync with cycle 4l
  1 2 1 2 2 1 3
  1 2 1 2 2 1 1 2 2 1 1 2
  1 2 1 2 2 1 3         ; cycle 6
  1 2 1 2 2 1 3
  1 2 1 2 2 1 1 2 2 1 1 2
  1 2 1 2 2 1 3         ; cycle 7
  1 2 1 2 2 1 2
  1 2 1 2 2 1 1 2 2 1 1 2
  1 2 1 2 2 1 2         ; cycle 8
  1 2 1 2 2 1 2
  1 2 1 2 2 1 1 2 2 1 1 2
  1 2 1 2 2 1 2         ; cycle 9
  1 2 1 2 1 1 2
  1 2 1 2 2 1 1 1 2 1 1 1
  1 2 1 1 1 1 2         ; cycle 10
  1 1 1 1 1 1 2
  1 1 1 1 1 1 1 1 1 1 1 1
; ------------------------------; Sect. III Static          [429 e]
  3 5 3 5 5 3 8         ; cycle 11
  3 5 3 5 5 3 8
  3 5 3 5 5 3 3 5 5 3 3 5
  3 5 3 5 5 3 8         ; cycle 12 (same)
  3 5 3 5 5 3 8
  3 5 3 5 5 3 3 5 5 3 3 5
  3 5 3 5 5 3 8         ; cycle 13 (same)
  3 5 3 5 5 3 8
  3 5 3 5 5 3 3 5 5 3 3 5
  3 5 3 5 5 3 8         ; cycle 14
  3 5 3 5 5 3 8         ;
  3 5 3 5 5 8           ;   cuts off here


Rhythms Lower Part:
; ------------------------------; Sect. I Static            [404 e]
  3 5 3 5 5 3 8         ; cycle 1
  3 5 3 5 5 3 8
  3 5 3 5 5 3 3 5  5 3 3 5 3 5 3 5 5 3 8
  3 5 3 5 5 3 8         ; cycle 2
  3 5 3 5 5 3 8
  3 5 3 5 5 3 3 5  5 3 3 5 3 5 3 5 5 3 8
  3 5 3 5 5 3 8         ; cycle 3
  3 5 3 5 5 2 7         ;         -- Speed-Up
  3 4 3 4 4 2 2 4  4 2 2 3 2 3 1 3 3 1 4
; ------------------------------; Sect. II Rapid Accelerando        [231 e]
  1 3 1 2 2 1 3         ; cycle 4 -- start is in sync with cycle 5u
  1 2 1 2 2 1 3
  1 2 1 2 2 1 1 2  2 1 1 2 1 2 1 2 2 1 3
  1 3 1 2 2 1 3         ; cycle 5
  1 2 1 2 2 1 3
  1 2 1 2 2 1 1 2  2 1 1 2 1 2 1 2 2 1 2
  1 2 1 2 2 1 2         ; cycle 6
  1 2 1 2 2 1 2
  1 2 1 2 2 1 1 2  2 1 1 2 1 2 1 2 2 1 2
  1 2 1 2 2 1 2         ; cycle 7
  1 2 1 2 2 1 2
  1 2 1 2 2 1 1 2  1 1 1 2 1 1 1 1 1 1 2
  1 1 1 1 1 1 2         ; cycle 8
  1 1 1 1 1 1 2
  1 1 1 1 1 1 1 1
; ------------------------------; Sect. III Allargando          [429 e]
           5 3 3 5 3 5 3 5 5 3 8
  3 5 3 5 5 3 8         ; cycle 9
  3 5 3 5 5 3 8
  3 5 3 5 5 3 3 5  6 3 3 5 3 5 3 6 5 3 8
  3 6 3 5 5 3 9         ; cycle 10
  3 5 3 5 6 3 8
  3 5 3 6 5 3 3 5  6 3 3 5 3 5 3 6 5 3 9
  3 7 3 8 9 3 13        ; cycle 11
  3 11 3 21

```

The Model
---------

This analysis translates fairly straightforward into a model of the
combined foreground structure. First, the tempo is set according to the
specification in the score:

```common_lisp
;;;
;;; Tempo
;;;
;;; Set as ration in order to work around floating point rounding problems
;;; in cm timing.

(defparameter *eigth-note-pulse* (rationalize (rhythm 'e (tempo 76 w))))

```

This cosmetic hack allows calls to `make-item-stream` to be embedded in
item stream constructor macros.

```common_lisp
;;;
;;; Allow the use of make-item-stream in constructor macros

(defprop make-item-stream :item-expand t)

```

Then an algorithm is defined for the upper foreground. As suggested by
the anaylsis above, the algorithm is driven by four sets of data: the
part's mode, its step pattern, its transposition pattern, and its
rhythmic pattern.

```lisp
;;;
;;; Upper Foreground

(defparameter *upper-mode* (transpose (mode white 2 2 1 2 2 2 1) 'c4))

(defparameter *upper-fg-steps*
  '( 0  0  1  0  2  1 -1            ; Phrase a
    -1 -1  2  1  3  2 -2         ; Phrase a'
     2  2  4  3  5  4 -1  0  3  2  6  5))    ; Phrase b

(defun make-upper-fg-notes (start-note)
  (intervals (make-item-stream 'items 'cycle *upper-fg-steps*)
         from (steps 1 initially-from (modeify (degree start-note)
                           *upper-mode*))))

(defun make-upper-fg-rhythms ()
  (items 3 5 3 5 5 3 7          ; cycle 1
  3 5 3 5 5 3 7
     3 5 3 5 5 3 3 4 5 3 3 5
     3 5 3 4 5 3 8          ; cycle 2
  3 5 3 4 5 3 8
     3 5 3 4 5 3 3 5 5 3 3 4
     3 5 3 5 5 3 7          ; cycle 3
  3 5 3 5 5 3 7
     3 5 3 5 5 3 3 4 5 3 3 5
     3 5 3 4 5 2 7          ; cycle 4
  2 4 2 4 4 2 5
     2 3 2 3 3 1 1 3 3 1 1 3
     1 2 1 2 2 1 3          ; cycle 5
  1 2 1 2 2 1 3
     1 2 1 2 2 1 1 2 2 1 1 2
     1 2 1 2 2 1 3          ; cycle 6
  1 2 1 2 2 1 3
     1 2 1 2 2 1 1 2 2 1 1 2
     1 2 1 2 2 1 3          ; cycle 7
  1 2 1 2 2 1 2
     1 2 1 2 2 1 1 2 2 1 1 2
     1 2 1 2 2 1 2          ; cycle 8
  1 2 1 2 2 1 2
     1 2 1 2 2 1 1 2 2 1 1 2
     1 2 1 2 2 1 2          ; cycle 9
  1 2 1 2 1 1 2
     1 2 1 2 2 1 1 1 2 1 1 1
     1 2 1 1 1 1 2          ; cycle 10
  1 1 1 1 1 1 2
     1 1 1 1 1 1 1 1 1 1 1 1
     (items (items 3 5 3 5 5 3 8    ; cycle 11-14
            3 5 3 5 5 3 8
               3 5 3 5 5 3 3 5 5 3 3 5)
        for 3)
     3 5 3 5 5 3 8          ; cycle 14
  3 5 3 5 5 3 8
     3 5 3 5 5 3            ;   cuts off here
  ))


(algorithm upper-fg-mono midi-note ()
  (vars (ntes (make-upper-fg-notes 'b4))
    (rhys (make-upper-fg-rhythms)))
  (setf note (unmodeify (item ntes) *upper-mode*)
    rhythm (* *eigth-note-pulse*
          (item rhys :kill t))))

```

The algorithm for the lower part foreground is driven by the same types
of data. However, since it is eventually “pitch-warped” into the treble
clef after it hit the bottom of the keyboard (4:4.7), its transposition
pattern adds a “warp” function that shifts notes 5 octaves (i.e. 20 mode
steps) up after 7 cycles, two 7-note phrases (A and A') and 4 measures
of the B phrase (8 notes).

```lisp
(defparameter *lower-mode* (transpose (mode black 2 3 2 2 3) 'cs4))

(defparameter *lower-fg-steps*
  '(0  0  1  0  2  2  0             ; Phrase a
    1  1  2  1 -2 -2 -1              ; Phrase a'
                     ; Phrase b
    1  1  2  2  0 -1 -4 -3  0 -1  3  2  1 -1  0 -3 -2 -3 -5))


(defun make-lower-fg-notes (start-note)
  (let* ((cycle-length (length *lower-fg-steps*))
     (warp-point (+ (* cycle-length 7) 7 7 8)))
    (intervals (intervals (make-item-stream 'items 'cycle *lower-fg-steps*
                        :for 1)
              on (items (items 0 for warp-point)
                    (items 20
                       in sequence
                       for most-positive-fixnum))
              for cycle-length)
           from (steps -2
               initially-from (modeify (degree start-note)
                           *lower-mode*)))))

(defun make-lower-fg-rhythms ()
  (items 3 5 3 5 5 3 8          ; cycle 1
  3 5 3 5 5 3 8
     3 5 3 5 5 3 3 5  5 3 3 5 3 5 3 5 5 3 8
     3 5 3 5 5 3 8          ; cycle 2 (same)
  3 5 3 5 5 3 8
     3 5 3 5 5 3 3 5  5 3 3 5 3 5 3 5 5 3 8
     3 5 3 5 5 3 8          ; cycle 3
  3 5 3 5 5 2 7
     3 4 3 4 4 2 2 4  4 2 2 3 2 3 1 3 3 1 4
     1 3 1 2 2 1 3          ; cycle 4 starts in synch w/ cycle 5u
  1 2 1 2 2 1 3
     1 2 1 2 2 1 1 2  2 1 1 2 1 2 1 2 2 1 3
     1 3 1 2 2 1 3          ; cycle 5
  1 2 1 2 2 1 3
     1 2 1 2 2 1 1 2  2 1 1 2 1 2 1 2 2 1 2
     1 2 1 2 2 1 2          ; cycle 6
  1 2 1 2 2 1 2
     1 2 1 2 2 1 1 2  2 1 1 2 1 2 1 2 2 1 2
     1 2 1 2 2 1 2          ; cycle 7
  1 2 1 2 2 1 2
     1 2 1 2 2 1 1 2  1 1 1 2 1 1 1 1 1 1 2
     1 1 1 1 1 1 2          ; cycle 8
  1 1 1 1 1 1 2
     1 1 1 1 1 1 1 1  5 3 3 5 3 5 3 5 5 3 8
     3 5 3 5 5 3 8          ; cycle 9
  3 5 3 5 5 3 8
     3 5 3 5 5 3 3 5  6 3 3 5 3 5 3 6 5 3 8
     3 6 3 5 5 3 9          ; cycle 10
  3 5 3 5 6 3 8
     3 5 3 6 5 3 3 5  6 3 3 5 3 5 3 6 5 3 9
     3 7 3 8 9 3 13         ; cycle 11
  3 11 3 21          ;   cuts off here
  ))

(algorithm lower-fg-mono midi-note ()
  (vars (ntes (make-lower-fg-notes 'ds4))
    (rhys (make-lower-fg-rhythms)))
  (setf note (unmodeify (item ntes) *lower-mode*)
    rhythm (* *eigth-note-pulse*
          (item rhys :kill t))))

```

At this stage, both foreground processes are implemented and may be
listened to by issuing a

```
Stella [Top-Level]: mix upper-fg-mono,lower-fg-mono 0
```

### Enhancements

A further improvement adds octaves and simulate the background layer:

```lisp
;;;
;;; Add Octaves and a fake background.
;;;
;;; Background notes are "muted" when the foreground is active.  To
;;; accomplish this, the names of the background containers must follow the
;;; foreground container names alphabetically.  Local variables are set up
;;; to communicate information between containers.

(defparameter *foreground-amplitude* .55)
(defparameter *background-amplitude* .4)

(merge desordre-v1.0 ()
  (let ((upper-fg-time 0) (upper-fg-note 0) (upper-fg-eighths 0)
    (lower-fg-time 0) (lower-fg-note 0) (lower-fg-eighths 0))

    (algorithm 1a_upper-fg_v1 midi-note (amplitude *foreground-amplitude*
                     channel 0)
      (vars (ntes (make-upper-fg-notes 'b3))
        (rhys (make-upper-fg-rhythms)))
      (if (evenp count)
      (setf upper-fg-time time
        upper-fg-eighths (item rhys :kill t)
        upper-fg-note (item ntes)
        note (unmodeify upper-fg-note *upper-mode*)
        duration (* *eigth-note-pulse* upper-fg-eighths)
        rhythm 0)
    (setf note (+ note 12)
          rhythm duration)))

    (algorithm 1b_upper-bg_v1 midi-note (length 1064 rhythm *eigth-note-pulse*
                     channel 1)
      (setf note (unmodeify
          (item (steps 1 (2 weight .33) (3 weight .15) (4 weight .05)
                   in random
                   for (expr upper-fg-eighths)
                   from (expr upper-fg-note)))
          *upper-mode*)
        amplitude (if (= time upper-fg-time) 0 *background-amplitude*)))

    (algorithm 2a_lower-fg_v1 midi-note (amplitude *foreground-amplitude*
                     channel 2)
      (vars (ntes (make-lower-fg-notes 'ds3))
        (rhys (make-lower-fg-rhythms)))
      (if (evenp count)
      (setf lower-fg-time time
        lower-fg-eighths (item rhys :kill t)
        lower-fg-note (item ntes)
        note (unmodeify lower-fg-note *lower-mode*)
        duration (* *eigth-note-pulse* lower-fg-eighths)
        rhythm 0)
    (setf note (+ note 12)
          rhythm duration)))

    (algorithm 2b_lower-bg_v1 midi-note (length 1064 rhythm *eigth-note-pulse*
                     channel 3)
      (setf note (unmodeify
          (item (steps 1 (2 weight .2) (3 weight .05)
                   in random
                   for (expr lower-fg-eighths)
                   from (expr lower-fg-note)))
          *lower-mode*)
        amplitude (if (= time lower-fg-time) 0 *background-amplitude*)))))

```

Finally, this code adds realism by simulating the chords that occur in
both foregrounds in section three:

``` {.codefrag}
;;;
;;; Finally, add more realistic foreground voicings.

(merge desordre-v2.0 ()
  (let ((upper-fg-time 0) (upper-fg-note 0) (upper-fg-eighths 0)
    (lower-fg-time 0) (lower-fg-note 0) (lower-fg-eighths 0))

    (algorithm 1_upper-fg_v2 midi-note (amplitude *foreground-amplitude*
                    channel 0)
      (vars (ntes (make-upper-fg-notes 'b3))
        (rhys (make-upper-fg-rhythms))
        voicing)
      (setf upper-fg-time time
        upper-fg-eighths (item rhys :kill t)
        rhythm (* *eigth-note-pulse* upper-fg-eighths)
        upper-fg-note (item ntes)
        note (unmodeify upper-fg-note *upper-mode*)
        )
      ;; add:         upper octave until  1 after  cycle 11 ...
      (if (< count 261)
      (sprout
       (object midi-note start time
           note (+ note 12) rhythm rhythm channel 0))
    ;; ... then add:  2 voices until  2 before cycle 12
 ;;                3 voices until 11 after  cycle 12
 ;;                4 voices thereafter
 (loop with nvoices = (if (< count 284) 1 (if (< count 297) 2 3))
          with voicing = (read-items (intervals 1 2 3 4 5 6
                            in heap
                            for (expr nvoices)
                            from (expr upper-fg-note)))
          for degree in voicing
          do (sprout
          (object midi-note start time
              note (unmodeify degree *upper-mode*)
              rhythm rhythm channel 0)))))

    (algorithm 2_upper-bg_v2 midi-note (length 1064 rhythm *eigth-note-pulse*
                    channel 1)
      (setf note (unmodeify
          (item (steps 1 (2 weight .33) (3 weight .15) (4 weight .05)
                   in random
                   for (expr upper-fg-eighths)
                   from (expr upper-fg-note)))
          *upper-mode*)
        amplitude (if (= time upper-fg-time) 0 *background-amplitude*)))

    (algorithm 3_lower-fg_v2 midi-note (amplitude *foreground-amplitude*
                    channel 2)
      (vars (ntes (make-lower-fg-notes 'ds3))
        (rhys (make-lower-fg-rhythms))
        voicing)
      (setf lower-fg-time time
        lower-fg-eighths (item rhys :kill t)
        lower-fg-note (item ntes)
        note (unmodeify lower-fg-note *lower-mode*)
        rhythm (* *eigth-note-pulse* lower-fg-eighths))
      ;; add:         upper octave until 23 after  cycle  8 ...
      (if (< count 254)
      (sprout
       (object midi-note start time
           note (+ note 12) rhythm rhythm channel 2))
    ;; ... then add:  2 voices until 22 after cycle   9
 ;;                3 voices thereafter
 (loop with nvoices = (if (< count 286) 1 2)
          with voicing = (read-items (intervals 1 2 3 4
                            in heap
                            for (expr nvoices)
                            from (expr lower-fg-note)))
          for degree in voicing
          do (sprout
          (object midi-note start time
              note (unmodeify degree *lower-mode*)
              rhythm rhythm channel 2)))))

    (algorithm 4_lower-bg_v2 midi-note (length 1064 rhythm *eigth-note-pulse*
                    channel 3)
      (setf note (unmodeify (item (steps 1 (2 weight .2) (3 weight .05)
                     in random
                     for (expr lower-fg-eighths)
                     from (expr lower-fg-note)))
                *lower-mode*)
        amplitude (if (= time lower-fg-time) 0 *background-amplitude*)))))

```

The controls which this model offers over pitch structure and
transposition factors are believed to be adequate to Ligeti's approach.
The temporal processes, however, contain a fair amount of handcoding and
are thus less easily transformed, although possibilities exßist to
replace them with more formal techniques.

References
----------

[Kinzler, Hartmut.]{#kinzler-91}
:   “György Ligeti: decision and automatism in ‘Désordre’, 1^er^ Étude,
    Premier Livre,” in: *Interface* 20(2):89-124. Swets &
    Zeitlinger, 1991.

[Ligeti, György.]{#ligeti-85}
:   “Études pour piano: premier livre.” B. Schott's Söhne, Mainz, 1985.
