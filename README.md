## Rationale

I think the most powerfull feature of anki cloze note types is the ability to produce multiple cards from a single note easily, But this comes with 2 main downsides (in my opinion):

1. Because only one (or some) of the clozes are active in each card (inactive clozes are rendered in plain text), the inactive clozes will "spoil" the cards in which they are active, this has been partially alleviated by the randomization of the cards (not effective in small decks) and has been solved completely with addons that are designed just for this use case (cloze cards overlapping), of which my favorite is the script in this [post]().
2. This may be a matter of a personal proplem, I am an extensive user of "Back Extra" Field specially in cloze notes, it annoyed me in the past (before I started using cloze-overlapper) when my note (Back Extra content) is irrelevent to the active cloze (because it is intended to one of the inactive ones), But after using the overlapper it became worse because my note become irrelevent to the whole card (because I used the overlapper to hide the inactive cloze to which the note was written).

So to solve this issue I wrote this simple js [script]() that goes into the back template, I made 2 versions of it:

1. a ready-to-go [version][./cloze-back-ready.html]: can be paste it directly into your "cloze" note type, no need to make a custom note type.
2. slightly advacned [version][./cloze-back-advanced.html]: you have to make a custom note type (based on cloze) or change your existing cloze note type and add a field called "Media".

- I also made a [version](./image-occlusion-back.html) for "Image-Occlusion" note type.

## Usage

the syntax (rules) is pretty simple:

1. to make your extra appear in all child cards: just write it into "Back Extra" field, this works only when there are no other extras in the field, e.g.
   `This text appears in all cards`.
2. to make you extra appear in card number n, just write "Cn::" before the text, for example to add an extra that appear only in card3 you do `C3::This is card 3` (the C can be in uppercase or lowercase)
3. the field is devidied into "extras", seperated by "|||" (triple pipe), e.g:
   `C1:: This is card number 1 |||
C2:: This is card number 2 |||
C3:: This is card number 3`

4. to make an extra that appears in all cards beside cards specific extras, use `G::` (stands for "Global"), for example:
   `C1:: This is card 1 |||
C2:: This is card 2 |||
G:: This text appears in all cards `

for the advanced cloze cards, the field "Media" works in the same way, it is for medias like images and videos, I made it a seperate field because I like to style my notes inside boxes and I don't want the media to go into the box, my [style.css](./style.css) for both the notes boxes and the media is also included.

- The scripts are only tested on AnkiDroid because I don't have access to a PC :(, If any issues or incompatabilities arise please leave a comment and I will try to fix them!.
- [Reddit Thread]()
