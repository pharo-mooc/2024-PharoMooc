{
    [ :i | ... i ... ]
    [ :i | Transcript show: i ; space ]
    [ :i | Transcript show: i ; space ]
      [:i | Transcript show: i ; cr ]
  | revisedColor |
  revisedColor := self.
  [ revisedColor luminance < aFloat ] 
     whileTrue: [ revisedColor := revisedColor slightlyLighter ].
  ^ revisedColor