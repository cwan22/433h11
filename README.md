README
================
Annabelle Wan
9/23/2021

``` r
url <- "https://guide.wisc.edu/faculty/"
library(RCurl)
library(XML)

content <- getURL(url)
split1 = unlist(strsplit(content, '.uw-people'))
x=strsplit(split1, '\n\n\n')
df <- data.frame(name=character(), position=character(), department=character(), degree=character(), mess=character())

for (i in 2:27){
  a=unlist(strsplit(x[[i]][1], '<li><p>'))
  b=strsplit(a, '<br/>')
  for (c in 1:length(b)){
    if(length(b[[c]])==5){
      df[nrow(df)+1, ] =b[[c]]
    }
  }
}
```

``` r
df$mess <- NULL
df
```

    ##                                        name                    position
    ## 1                           ABBOTT,DAVID H.                   Professor
    ## 2                        ABD-ELSAYED,ALAA A       Assoc Professor (Chs)
    ## 3                          ABDUALLAH,FAISAL                   Professor
    ## 4                      ABRAHAM,OLUFUNMILOLA         Assistant Professor
    ## 5                           ABRAMS,SAMANTHA              Assoc Lecturer
    ## 6                              ABRAMSON,LYN                   Professor
    ## 7                             ACKER,LINDSAY                    Lecturer
    ## 8                           ACKERMAN,STEVEN                   Professor
    ## 9                    ADAMCZYK,PETER GABRIEL         Assistant Professor
    ## 10                   ADAMES-CORRALIZA,ANGEL         Assistant Professor
    ## 11                              ADAMS,AERON          Clinical Asst Prof
    ## 12                              ADAMS,MEGAN          Asst Faculty Assoc
    ## 13                             ADCOCK,SARAH         Assistant Professor
    ## 14                   ADDINGTON,REBECCA LYNN             Senior Lecturer
    ## 15                              ADDO,FENABA         Associate Professor
    ## 16                             ADELL,SANDRA                   Professor
    ## 17                               AFFI,ABOUD  Clinical Adjunct Professor
    ## 18                         AGARWAL,PRIYANKA         Assistant Professor
    ## 19                            AGASIE,ROBERT       Instrmt Innovator/Ins
    ## 20                             AGOKE,ADEOLA          Asst Faculty Assoc
    ## 21                     AHLQUIST,PAUL GERALD                   Professor
    ## 22                              AHMAD,NIHAL                   Professor
    ## 23                          AHMED,AZAM SYED       Assoc Professor (Chs)
    ## 24                               AHN,JAERIN         Assoc Faculty Assoc
    ## 25                                  AHN,SUE                   Professor
    ## 26                              AHN,YEOHYUN         Assistant Professor
    ## 27                   AHRENS,SARAH ELIZABETH         Clinical Assoc Prof
    ## 28                              AI,ALBERT L          Visiting Asst Prof
    ## 29                          AIKEN,JEFFREY P          Adjunct Instructor
    ## 30                             AIZAWA,NAOKI         Assistant Professor
    ## 31                             AJMANI,VIVEK         Assoc Faculty Assoc
    ## 32                            AKELLA,ADITYA                   Professor
    ## 33                            AL-ADRA,DAVID         Assistant Professor
    ## 34                           AL-SUBU,AWNI M        Asst Professor (Chs)
    ## 35                           ALAGOZ,OGUZHAN                   Professor
    ## 36                            ALARID,ELAINE                   Professor
    ## 37                          ALATOUT,SAMER N         Associate Professor
    ## 38                         ALBARGHOUTHI,AWS         Assistant Professor
    ## 39                             ALBERS,CRAIG         Associate Professor
    ## 40                             ALBERT,LAURA                   Professor
    ## 41                   ALBERTINI,MARK RICHARD                   Professor
    ## 42                    ALCALA GALAN,MERCEDES         Associate Professor
    ## 43                                ALDAG,RAY                   Professor
    ## 44                       ALDER,SIMEON DAVID           Faculty Associate
    ## 45               ALEXANDER,ANDREW LAFAYETTE                   Professor
    ## 46                         ALEXANDER,ANGELA           Faculty Associate
    ## 47                      ALEXANDER,LACEY ANN          Clinical Asst Prof
    ## 48                            ALI,SHANTEL D        Asst Prof Of Mil Sci
    ## 49                        ALI,SYED EKHTEYAR             Senior Lecturer
    ## 50                        ALIBALI,MARTHA W.                   Professor
    ## 51                            ALISCH,REID S         Assistant Professor
    ## 52                           ALLEN,CAITILYN                   Professor
    ## 53                              ALLEN,DAVID                   Professor
    ## 54                            ALLEN,HEATHER         Associate Professor
    ## 55                               ALLEN,MATT                   Professor
    ## 56                        ALLEWAERT,MONIQUE         Associate Professor
    ## 57                             ALLIE,MARK C           Faculty Associate
    ## 58                           ALONSO,ARACELI                Dis Lecturer
    ## 59                     ALTINO,SOH-HYUN PARK         Associate Professor
    ## 60                           ALTSCHAFL,BETH           Faculty Associate
    ## 61                            ALTSECH,MOSES                    Lecturer
    ## 62                              ALTWIES,JOY           Faculty Associate
    ## 63                      ALVAREZ,ELIZABETH E          Clinical Asst Prof
    ## 64                           ALVAREZ,SAYLIN             Senior Lecturer
    ## 65                     AMADOR-NOGUEZ,DANIEL         Associate Professor
    ## 66                               AMANN,KURT         Associate Professor
    ## 67                       AMASINO,RICHARD M.                   Professor
    ## 68                   AMATO,FELICE CATHERINE                    Lecturer
    ## 69                              AMINE,LAILA         Associate Professor
    ## 70                             AMSBARY,PAUL          Adjunct Assoc Prof
    ## 71                               AN,PANDUAN          Visiting Asst Prof
    ## 72                              AN,ZHE GIGI         Assistant Professor
    ## 73                     ANANTHARAMAN,KARTHIK         Assistant Professor
    ## 74                       ANCOS GARCIA,PABLO         Associate Professor
    ## 75                         ANDERSEN,CLAUS E         Assistant Professor
    ## 76                           ANDERSON,DAVID                   Professor
    ## 77                         ANDERSON,DAVID F                   Professor
    ## 78                         ANDERSON,KATHRYN                    Lecturer
    ## 79                            ANDERSON,LORI         Assistant Professor
    ## 80                            ANDERSON,MARK         Assistant Professor
    ## 81                           ANDERSON,PETER             Senior Lecturer
    ## 82                      ANDERSON,RICHARD A.                   Professor
    ## 83                         ANDERSON,ROZALYN         Associate Professor
    ## 84                           ANDES,DAVID R.                   Professor
    ## 85                          ANDREAE,SUSAN J         Assistant Professor
    ## 86                    ANDRESEN,CHRISTIAN G.         Assistant Professor
    ## 87                           ANDREWS,JOSEPH         Assistant Professor
    ## 88                           ANDREWS,LISA M         Assoc Faculty Assoc
    ## 89                              ANDREWS,URI         Associate Professor
    ## 90                        ANDRZEJEWSKI,ANNA                   Professor
    ## 91                               ANE,CECILE                   Professor
    ## 92                          ANE,JEAN-MICHEL                   Professor
    ## 93                              ANEX,ROBERT                   Professor
    ## 94                       ANGENENT,SIGURD B.                   Professor
    ## 95             ANGULO BRACHO,HERNAN LIZARDO         Clinical Instructor
    ## 96                           ANGUS,JENNIFER                   Professor
    ## 97                             ANIBAS,CALLI         Assoc Research Spec
    ## 98                           ANIBAS,MELISSA          Clinical Asst Prof
    ## 99                               ANJUM,UMAR         Research Specialist
    ## 100                              ANNA,ERIKA          Asst Faculty Assoc
    ## 101                          ANSARI,ASEEM Z                   Professor
    ## 102                         ANTONY,KATHLEEN        Asst Professor (Chs)
    ## 103                        ARCHAMBAULT,JOHN            Assistant Dean/L
    ## 104                    ARCHDEACON,THOMAS J.                   Professor
    ## 105                                  ARD,BJ         Assistant Professor
    ## 106                           AREFEVA,ALINA         Assistant Professor
    ## 107                             ARENDT,LISA         Assistant Professor
    ## 108                             ARFA,SANDRA           Faculty Associate
    ## 109                            ARINKIN,DIMA                   Professor
    ## 110                       ARMSTRONG,GRANT W         Associate Professor
    ## 111                        ARMSTRONG,JOSHUA         Associate Professor
    ## 112                    ARNDT,KIMBERLY KEGEL  Clinical Adjunct Asst Prof
    ## 113                          ARNOLD,MICHAEL                   Professor
    ## 114                 ARNOLDY,COURTNEY JEANNE         Clinical Instructor
    ## 115                            ARORA,NEERAJ                   Professor
    ## 116                ARPACI-DUSSEAU,ANDREA C.                   Professor
    ## 117                 ARPACI-DUSSEAU,REMZI H.                   Professor
    ## 118                       ARRIAGA,FRANCISCO         Associate Professor
    ## 119               ARRIOLA APELO,SEBASTIAN I         Assistant Professor
    ## 120                            ARTHUR,EMILY         Associate Professor
    ## 121                 ASCHENBROICH,SOPHIE ANN          Clinical Asst Prof
    ## 122                             ASEN,ROBERT                   Professor
    ## 123           ASHTON,LYDIA MAGDALENA TEJEDA         Assistant Professor
    ## 124                         ASHTON,RANDOLPH         Associate Professor
    ## 125                           ASIF,MUHAMMAD                    Lecturer
    ## 126                        ASMUS,JENNIFER M                   Professor
    ## 127           ASSADI-PORTER,FARIBA MASOUMEH              Assoc Lecturer
    ## 128                            ASTOR,BRAD C                   Professor
    ## 129                          ASTRELLA,JULIE         Clinical Assoc Prof
    ## 130                         ATAPATTU,SUMUDU         Dis Admin Prgm Spec
    ## 131                        ATTIE,ALAN DAVID                   Professor
    ## 132                            ATUCHA,AMAYA         Assistant Professor
    ## 133                            AUDHYA,ANJON                   Professor
    ## 134                     AUERBACH,EMILY KATE                   Professor
    ## 135                           AUGER,ANTHONY                   Professor
    ## 136                     AUGHENBAUGH,WILLIAM             Professor (Chs)
    ## 137                        AULIK,NICOLE ANN          Clinical Asst Prof
    ## 138                          AUNG,HTET HTET              Assoc Lecturer
    ## 139                          AUSDERAU,KARLA         Associate Professor
    ## 140                          AUSTERWEIL,JOE         Assistant Professor
    ## 141                            AVEY,GREGORY       Assoc Professor (Chs)
    ## 142                       AVRAMENKO,RICHARD                   Professor
    ## 143              AYARI BEN HADJ KACEM,MOUNA         Assoc Faculty Assoc
    ## 144                            AYD,SHARON W          Adjunct Assoc Prof
    ## 145                 AZOCAR,SAMUEL ALEJANDRO             Senior Lecturer
    ## 146                            AZODI,JAHANA          Asst Faculty Assoc
    ## 147                           BABAL,JESSICA        Asst Professor (Chs)
    ## 148                              BABAR,YASH         Assistant Professor
    ## 149                             BABCOCK,SUE                   Professor
    ## 150                               BACH,ERIC                   Professor
    ## 151                        BACH,JONATHAN F.         Clinical Assoc Prof
    ## 152                        BACH,TAIYA RENAE          Asst Faculty Assoc
    ## 153                          BACK,LARISSA E         Associate Professor
    ## 154                        BAHIA,HUSSAIN U.                   Professor
    ## 155                                BAI,YANG         Associate Professor
    ## 156                         BAILEY,HANNAH E            Assistant Dean/M
    ## 157                        BAIR,JESSE JONAS          Adjunct Instructor
    ## 158                               BAIRD,IAN                   Professor
    ## 159                             BAKER,ANGIE         Clinical Instructor
    ## 160                        BAKER,BERNADETTE                   Professor
    ## 161                             BAKER,TRACY         Associate Professor
    ## 162                             BAKKEN,LORI       Honorary Assoc/Fellow
    ## 163                       BAKSHI,VAISHALI P         Associate Professor
    ## 164                               BAL,AYDIN                   Professor
    ## 165                        BALANTEKIN,A. B.                   Professor
    ## 166                        BALDACCHINO,JOHN                   Professor
    ## 167                           BALDO,BRIAN A         Associate Professor
    ## 168                     BALDRIDGE,BIANCA J.         Associate Professor
    ## 169                   BALDRIDGE,ELIZABETH M                    Lecturer
    ## 170                            BALDWIN,CODY           Faculty Associate
    ## 171              BALLESTEROS CHAVEZ,JESUS A              Assoc Lecturer
    ## 172                            BALSTER,NICK                   Professor
    ## 173                            BANERJEE,MOU         Assistant Professor
    ## 174                          BANERJEE,SUMAN                   Professor
    ## 175                     BANKS,MATTHEW ISAAC                   Professor
    ## 176                           BARAK,PHILLIP                   Professor
    ## 177                   BARAK-CUNNINGHAM,JERI                   Professor
    ## 178                     BARBATO,ERIN MURPHY          Clinical Asst Prof
    ## 179                          BARCELOS,CHRIS         Assistant Professor
    ## 180                            BARCZI,STEVE             Professor (Chs)
    ## 181                         BARFORD,CAROL L             Senior Lecturer
    ## 182                          BARFORD,PAUL R                   Professor
    ## 183                    BARGER,AMY JOSEPHINE                   Professor
    ## 184                           BARGER,VERNON                   Professor
    ## 185                         BARHAM,BRADFORD                   Professor
    ## 186                           BARICH,JOSEPH             Senior Lecturer
    ## 187                            BARLETT,CARL                    Lecturer
    ## 188                           BARNARD,ERLIN       Dis Faculty Associate
    ## 189                            BARNARD,MARK                    Lecturer
    ## 190                             BARNES,JILL         Assistant Professor
    ## 191                         BARNETT,SUSANNE       Assoc Professor (Chs)
    ## 192                   BARRETT,BRUCE PATRICK                   Professor
    ## 193                           BARRETT,KEVIN              Assoc Lecturer
    ## 194                 BARRETT,PATRICK STEPHEN         Assoc Faculty Assoc
    ## 195                          BARRY,AMY QUAN                   Professor
    ## 196                             BARRY,LYNDA                   Professor
    ## 197                           BART,DAVID J.         Associate Professor
    ## 198                             BARTA,CHERI           Faculty Associate
    ## 199                         BARTFELD,JUDITH                   Professor
    ## 200                           BARTH,MICHAEL              Assoc Lecturer
    ## 201                     BARTHOLOMAY,LYRIC C                   Professor
    ## 202                        BARTHOLOMEW,KYLE         Clinical Instructor
    ## 203                      BARTLETT,HEATHER L             Professor (Chs)
    ## 204                         BARTLETT,LESLEY                   Professor
    ## 205                       BARTOL,LAURA JEAN         Assoc Faculty Assoc
    ## 206                              BARZEN,JEB           Adjunct Asst Prof
    ## 207                       BASHIRULLAH,ARASH         Associate Professor
    ## 208                       BASKAYA,MUSTAFA K                   Professor
    ## 209                        BATES,DESIREE M.       Inform Process Conslt
    ## 210                              BATES,ERIK          Visiting Asst Prof
    ## 211                                BATT,BOB         Associate Professor
    ## 212                    BATZLI,JANET MC CRAY       Dis Faculty Associate
    ## 213                              BAUER,ADAM        Asst Professor (Chs)
    ## 214                             BAUER,ANNIE         Assistant Professor
    ## 215                            BAUER,DANIEL                   Professor
    ## 216                  BAUER-ARMSTRONG,CHERYL           Faculty Associate
    ## 217                              BAUM,DAVID                   Professor
    ## 218           BAUTISTA MENDOZA,GLORIA ROCIO             Senior Lecturer
    ## 219                      BAUTISTA,LEONELO E         Associate Professor
    ## 220                           BAVAFA,HESSAM         Assistant Professor
    ## 221                          BAYOUTH,JOHN E                   Professor
    ## 222                    BAZALAKOVA,MIHAELA H        Asst Professor (Chs)
    ## 223                       BEA,MEGAN DOHERTY         Assistant Professor
    ## 224                       BEACH,JEREMY PAUL         Assoc Faculty Assoc
    ## 225                         BEAMSLEY,MARK B         Clinical Assoc Prof
    ## 226                      BEAN,DEREK MERRILL         Assoc Faculty Assoc
    ## 227                     BEARDEN,ELIZABETH B                   Professor
    ## 228                          BEATTIE,ROBERT           Faculty Associate
    ## 229                           BECHTOL,KEITH         Assistant Professor
    ## 230                    BECKER,AMY ELIZABETH           Faculty Associate
    ## 231                              BECKER,MEL                    Lecturer
    ## 232                           BECKHAM,SARAH          Asst Faculty Assoc
    ## 233                 BEDNAREK,SEBASTIAN YORK                   Professor
    ## 234                         BEDNARZ,BRYAN P         Associate Professor
    ## 235                           BEEBE,DAVID J                   Professor
    ## 236                           BEEBE,REBECCA       Sr Student Serv Coord
    ## 237                        BEGAM,RICHARD J.                   Professor
    ## 238                            BEHDAD,NADER                   Professor
    ## 239                         BEHM,JENNA LYNN                    Lecturer
    ## 240                           BEHNKE,RACHEL              Assoc Lecturer
    ## 241                            BEIA,SUZANNE         Artist-In-Residence
    ## 242                      BEILIN,KATARZYNA O                   Professor
    ## 243                            BELL,DAVID R         Associate Professor
    ## 244                          BELL,MICHAEL M                   Professor
    ## 245                         BELLING,SHAWN D                    Lecturer
    ## 246                            BELLMORE,AMY                   Professor
    ## 247                  BELTRAN PORTALES,DAVID          Visiting Asst Prof
    ## 248                       BEMENT,WILLIAM M.                   Professor
    ## 249            BENALLY THOMPSON,BRET ROBERT          Clinical Asst Prof
    ## 250                       BENDLIN,BARBARA B         Associate Professor
    ## 251                            BENEKER,JEFF                   Professor
    ## 252                          BENGSON,JOHN T         Associate Professor
    ## 253              BENGURIA DEPASSIER,SOLEDAD          Asst Faculty Assoc
    ## 254                       BENNETT,ALLYSON J                   Professor
    ## 255                      BENSKY,ANNE MARYSE          Adjunct Instructor
    ## 256                           BENSON,MARK E       Assoc Professor (Chs)
    ## 257                             BENT,ANDREW                   Professor
    ## 258                         BENTLEY,ELLISON          Clinical Professor
    ## 259                         BENTZ,MICHAEL L                   Professor
    ## 260                       BERGER,LAWRENCE M                   Professor
    ## 261                            BERGMANN,UWE                   Professor
    ## 262                           BERKELMAN,JIM           Faculty Associate
    ## 263                           BERLAND,LEEMA         Associate Professor
    ## 264                         BERLAND,MATTHEW         Associate Professor
    ## 265                         BERNARD,KRISTEN                   Professor
    ## 266                  BERNARD-DONALS,MICHAEL                   Professor
    ## 267                         BERNER,COURTNEY         Assoc Faculty Assoc
    ## 268                      BERNHARDT,DAVID T.             Professor (Chs)
    ## 269                          BERRIDGE,CRAIG                   Professor
    ## 270                     BERRY,JOHN FERGUSON                   Professor
    ## 271                     BERSHADY,MATTHEW A.                   Professor
    ## 272                       BERSON,ARGANTHAEL                    Lecturer
    ## 273                   BERSU,EDWARD THORWALD              Professor Emer
    ## 274                     BERTELSON,RYAN JOHN                    Lecturer
    ## 275                            BERTRAM,LISA         Associate Professor
    ## 276                      BERTRAM,TIMOTHY H.                   Professor
    ## 277                       BERVEN,NORMAN LEE              Professor Emer
    ## 278                      BESAW,LUKE ANTHONY          Adjunct Instructor
    ## 279                              BEST,KAREN             Senior Lecturer
    ## 280                             BETHKE,PAUL         Associate Professor
    ## 281                       BETZ,NATALIE ANNE           Faculty Associate
    ## 282                     BHATTACHARYYA,ANITA         Assistant Professor
    ## 283                         BHAVNANI,RIKHIL         Associate Professor
    ## 284                              BIER,VICKI                   Professor
    ## 285                         BILBIJA,KSENIJA                   Professor
    ## 286                   BILDER,ANNE ELIZABETH          Adjunct Instructor
    ## 287                      BILEN-ROSAS,GUELAY        Asst Professor (Chs)
    ## 288                     BINKLEY,JENNIFER L.          Clinical Asst Prof
    ## 289                             BIRD,IAN M.                   Professor
    ## 290               BIRKELAND,LAURA ELIZABETH       Sr Clin Genetic Couns
    ## 291                             BIRN,RASMUS         Associate Professor
    ## 292                           BISHOP,LAUREN         Assistant Professor
    ## 293                     BISHOP,MALACHY LIAM                   Professor
    ## 294                             BISHOP,SEAN           Faculty Associate
    ## 295                             BITZAN,AMOS         Assistant Professor
    ## 296                            BJORK,CLAIRE                    Lecturer
    ## 297                        BJORLING,DALE E.                   Professor
    ## 298                             BLACK,KEVIN                   Professor
    ## 299                      BLACKWELL,HELEN E.                   Professor
    ## 300                              BLAIR,SETH                   Professor
    ## 301                     BLAKE,JOCELYN MARIE        Asst Professor (Chs)
    ## 302                      BLANCHARD,DEANNA S         Clinical Instructor
    ## 303                          BLASIUS,LESLIE                   Professor
    ## 304                    BLAZEK,JENNIFER RUTH                    Lecturer
    ## 305                           BLEAM,WILLIAM                   Professor
    ## 306                          BLEEDORN,JASON         Clinical Assoc Prof
    ## 307                           BLOCH,BRANDON         Assistant Professor
    ## 308                              BLOCK,PAUL         Associate Professor
    ## 309                  BLOCK,STEPHEN BENJAMIN           Faculty Associate
    ## 310                             BLOCK,WALLY                   Professor
    ## 311                         BLONIEN,NATALIE           Faculty Associate
    ## 312                           BLOOM,VICKI D              Assoc Lecturer
    ## 313                      BLUE,JACOB MICHAEL              Assoc Lecturer
    ## 314                              BLUM,BARAK         Assistant Professor
    ## 315                        BLUM,HANNAH BETH         Assistant Professor
    ## 316                            BLYTHE,VERDA           Faculty Associate
    ## 317                     BOADO,JOEL MAGDALES              Assoc Lecturer
    ## 318                       BOCHSLER,PHILIP N          Clinical Professor
    ## 319                             BOCK,ADAM J                    Lecturer
    ## 320               BOCK-SHONKWILER,JULIE ANN              Assoc Lecturer
    ## 321                            BOEDER,STEVE           Faculty Associate
    ## 322           BOEKHOFF-FALK,GRACE ELISABETH         Associate Professor
    ## 323                     BOELDT,DEREK STEVEN         Assistant Professor
    ## 324                            BOERSMA,JOHN              Assoc Lecturer
    ## 325                BOGGESS,JACQUELYN LOUISE                    Lecturer
    ## 326                       BOHLIG,AMANDA JAN  Clinical Adjunct Asst Prof
    ## 327                      BOLDYREV,STANISLAV                   Professor
    ## 328                  BOLLING,BRADLEY WARREN         Associate Professor
    ## 329                             BOLT,DANIEL                   Professor
    ## 330                            BOLY,MELANIE         Assistant Professor
    ## 331                        BOMKAMP,TAMMY M.         Clinical Instructor
    ## 332                          BONAMICI,CHLOE         Assistant Professor
    ## 333                        BONAZZA,RICCARDO                   Professor
    ## 334                          BONK,NICOLE A.        Asst Professor (Chs)
    ## 335                         BOOK,EMILY KATE           Adjunct Asst Prof
    ## 336                          BOOSKE,JOHN H.                   Professor
    ## 337                              BOOTH,ERIC                    Lecturer
    ## 338                     BOOTHALINGAM,SRIRAM         Assistant Professor
    ## 339                      BOROWSKI,KRZYSZTOF              Assoc Lecturer
    ## 340                             BOSE,TULIKA                   Professor
    ## 341                          BOSWELL,EDWARD         Assoc Faculty Assoc
    ## 342                           BOSWELL,LAIRD                   Professor
    ## 343                    BOTERO,BEATRIZ LUCIA                    Lecturer
    ## 344                               BOTEZ,DAN                   Professor
    ## 345                            BOTHAM,SARAH           Faculty Associate
    ## 346                  BOUCHER,JOSEPH WILLIAM             Senior Lecturer
    ## 347                           BOUGHTON,SARA              Assoc Lecturer
    ## 348                             BOUNDY,TERI                    Lecturer
    ## 349           BOURG HACKER,DOMINIQUE CORINE                    Lecturer
    ## 350                         BOUSQUET,GILLES                   Professor
    ## 351                     BOUTILIER,JUSTIN J.         Assistant Professor
    ## 352                              BOW,LESLIE                   Professor
    ## 353                              BOWE,SCOTT                   Professor
    ## 354                           BOWEN,JEFF J.          Adjunct Instructor
    ## 355                      BOWER,GLENN ROBERT           Faculty Associate
    ## 356                          BOWERS,BARBARA                   Professor
    ## 357                      BOWIE,KATHERINE A.                   Professor
    ## 358                          BOWLING,JOSEPH                    Lecturer
    ## 359                             BOWMAN,MATT             Senior Lecturer
    ## 360                             BOYDSTON,AJ                   Professor
    ## 361                             BRACE,CHRIS         Associate Professor
    ## 362                         BRACHMAN,LAURIE             Senior Lecturer
    ## 363                      BRADBURY,ELIZABETH              Assoc Lecturer
    ## 364                     BRADEN,MAIA NYSTRUM       Honorary Assoc/Fellow
    ## 365                   BRADFIELD,CHRISTOPHER                   Professor
    ## 366                     BRADLEY,KRISTIN ANN             Professor (Chs)
    ## 367                          BRANCH,KRISTIN           Faculty Associate
    ## 368                     BRANCHAW,JANET LYNN         Assistant Professor
    ## 369                        BRANDT,CURTIS R.                   Professor
    ## 370                           BRANTLY,SUSAN                   Professor
    ## 371                          BRAR,VICTOR W.         Assistant Professor
    ## 372                         BRASIER,ALLAN R                   Professor
    ## 373                            BRATZKE,LISA         Associate Professor
    ## 374                           BRAUER,MARKUS                   Professor
    ## 375                         BRAUNGINN,JENNY         Assoc Faculty Assoc
    ## 376                           BRAUS,MICHAEL       Honorary Assoc/Fellow
    ## 377                           BRAVER,JOSHUA         Assistant Professor
    ## 378                             BRAY,LORA N              Assoc Lecturer
    ## 379                     BREEDLOVE,TRISTAN S         Clinical Instructor
    ## 380                      BREKKE,LINDSAY RAE              Assoc Lecturer
    ## 381                         BRENNAN,MICHAEL           Adjunct Professor
    ## 382                          BRENNER,RACHEL                   Professor
    ## 383                     BRESCHAK,JON THOMAS           Faculty Associate
    ## 384                          BRESLOW,ROBERT       Assoc Professor (Chs)
    ## 385                       BRESNICK,EMERY H.                   Professor
    ## 386                        BREUER,RYAN MARK          Clinical Asst Prof
    ## 387                   BRIEL,HALEY ELIZABETH          Asst Faculty Assoc
    ## 388                 BRIGGS,KATHERINE CHAREK                    Lecturer
    ## 389                         BRIGHOUSE,HARRY                   Professor
    ## 390                       BRINSKO,ELEANOR O              Assoc Lecturer
    ## 391                          BRITLAND,KAREN                   Professor
    ## 392                             BRITO,TONYA                   Professor
    ## 393                       BROCKLISS,WILLIAM         Associate Professor
    ## 394                             BROMAN,KARL                   Professor
    ## 395                      BRONKHORST,CURT A.                   Professor
    ## 396                           BROOKE,STEVEN         Assistant Professor
    ## 397                       BROOKS,ERIN GRACE             Professor (Chs)
    ## 398               BROOKS,NATHANIEL PHILLIPS       Assoc Professor (Chs)
    ## 399                        BROOKSBY,RICHARD         Clinical Instructor
    ## 400                      BROSSARD,DOMINIQUE                   Professor
    ## 401                   BROUNTS,SABRINA HELEN          Clinical Professor
    ## 402                           BROW,DAVID A.                   Professor
    ## 403                          BROWN,BRADFORD                   Professor
    ## 404                          BROWN,DAVID P.                   Professor
    ## 405                            BROWN,DUSTIN              Assoc Lecturer
    ## 406                     BROWN,HEIDI WENDELL         Assistant Professor
    ## 407                            BROWN,JOSHUA          Clinical Asst Prof
    ## 408                        BROWN,LAWRENCE T         Visiting Assoc Prof
    ## 409                           BROWN,MATTHEW        Asst Professor (Chs)
    ## 410                           BROWN,MATTHEW         Assistant Professor
    ## 411                      BROWN,RANDALL TODD         Associate Professor
    ## 412                      BRUCE,MICHAEL JOHN              Assoc Lecturer
    ## 413                        BRUNKARD,JACOB O         Assistant Professor
    ## 414                        BRUNOLD,THOMAS C                   Professor
    ## 415                        BRYAN,GINA MARIE          Clinical Professor
    ## 416                               BRYAN,TOM          Asst Faculty Assoc
    ## 417                        BUCCINI,STEFANIA                   Professor
    ## 418             BUCHBERGER JONES,AMANDA RAE          Asst Faculty Assoc
    ## 419                      BUCK,DOUGLAS SCOTT          Adjunct Instructor
    ## 420      BUCKINGHAM,TANYA MICHELLE ANDERSEN       Instructl Prg Mgr Iii
    ## 421                         BUDGE,STEPHANIE         Associate Professor
    ## 422                             BUGNI,TIM S                   Professor
    ## 423                                BUHL,TIM                    Lecturer
    ## 424                        BUHNEMANN,GUDRUN                   Professor
    ## 425                     BUHR-LAWLER,MELANIE          Clinical Professor
    ## 426                          BUISCH,DERRICK                   Professor
    ## 427                         BULLER,ANDREW R         Assistant Professor
    ## 428                         BULLOCK,ERIKA C         Assistant Professor
    ## 429                       BULLTAIL,GRACE A.         Assistant Professor
    ## 430                           BUNN,HENRY T.                   Professor
    ## 431                            BURDEN,BARRY                   Professor
    ## 432                          BURGER,CORINNA         Associate Professor
    ## 433                         BURGESS,RICHARD              Professor Emer
    ## 434                         BURGOYNE,JOSEPH              Assoc Lecturer
    ## 435                       BURIVALOVA,ZUZANA         Assistant Professor
    ## 436                             BURK,LINNEA         Clinical Assoc Prof
    ## 437                     BURKARD,MARK EDWARD                   Professor
    ## 438                       BURKHOLDER,KRISTY           Faculty Associate
    ## 439                      BURKI,KRISTIN ANNE          Asst Faculty Assoc
    ## 440                   BURLINGHAM,WILLIAM J.                   Professor
    ## 441                              BURNS,ERIK         Assoc Faculty Assoc
    ## 442              BURNS,MARGUERITE ELIZABETH         Associate Professor
    ## 443                       BURSTYN,JUDITH N.                   Professor
    ## 444                           BURT,BRIAN A.         Assistant Professor
    ## 445                   BURTON,ALEXANDRA JANE          Clinical Asst Prof
    ## 446                           BURTON,BRIANA         Associate Professor
    ## 447                         BURTON,ROBERT J              Assoc Lecturer
    ## 448                      BURTON,SKYLAR TREE          Visiting Asst Prof
    ## 449                                BUSH,LIZ         Assistant Professor
    ## 450                        BUSSE,WILLIAM W.                   Professor
    ## 451                  BUTCHER,KACIE LUCCHINI           Adjunct Asst Prof
    ## 452                       BUTCHER,SAMUEL E.                   Professor
    ## 453                    BUTLER,JEFFREY DAVID                    Lecturer
    ## 454                         BUTLER,MARGARET         Associate Professor
    ## 455                        BYKHOVSKAYA,ANNA              Assoc Lecturer
    ## 456                        BYKOVSKYI,ANDREA         Assistant Professor
    ## 457                        BYKOWSKI,ERIN F.                    Lecturer
    ## 458                     BYRD-MCPHEE,MICHELE          Adjunct Instructor
    ## 459                        CABRERA,VICTOR E                   Professor
    ## 460                   CAHILL,MICHAEL EDWARD         Assistant Professor
    ## 461                             CAHILL,NICK                   Professor
    ## 462                              CAI,JIN-YI                   Professor
    ## 463                               CAI,WEIBO                   Professor
    ## 464                        CALDARARU,ANDREI                   Professor
    ## 465                  CALDERON,CLAUDIA IRENE         Assoc Faculty Assoc
    ## 466                         CALDERON,JAVIER                   Professor
    ## 467                     CALDWELL,MICHAEL F.             Senior Lecturer
    ## 468                          CALHOUN,JOSHUA         Associate Professor
    ## 469                           CALLACI,EMILY         Associate Professor
    ## 470                      CALOMINO,SALVATORE         Associate Professor
    ## 471                  CAMAL,JEROME SEBASTIEN         Associate Professor
    ## 472                     CAMARA,NJAMEH MARIA                    Lecturer
    ## 473                         CAMERON,KENNETH                   Professor
    ## 474                           CAMERON,STARR          Clinical Asst Prof
    ## 475                               CAMP,BILL             Senior Lecturer
    ## 476                         CAMPAGNOLA,PAUL                   Professor
    ## 477                           CAMPBELL,ANNA         Associate Professor
    ## 478                      CAMPBELL,JEFFERY L       Instructor Of Mil Sci
    ## 479                             CANON,DAVID                   Professor
    ## 480                         CANTOR,JASON R.         Assistant Professor
    ## 481                           CANTWELL,TONY              Assoc Lecturer
    ## 482                      CAPITINI,CHRISTIAN         Associate Professor
    ## 483                        CAPTAIN,AMANDA K          Asst Faculty Assoc
    ## 484                         CARAYON,PASCALE                   Professor
    ## 485                 CARAZA-HARTER,TYLER RAY          Asst Faculty Assoc
    ## 486                           CARCHMAN,EVIE         Assistant Professor
    ## 487                       CARDA,RONNIE DEAN           Faculty Associate
    ## 488                         CARDIFF,MICHAEL         Associate Professor
    ## 489                         CAREY,HANNAH V.                   Professor
    ## 490                          CARL,BRADLEY R                    Lecturer
    ## 491                        CARLSMITH,DUNCAN                   Professor
    ## 492                            CARLSON,JANE           Adjunct Professor
    ## 493                           CARLSON,MARCY                   Professor
    ## 494              CARLSSON,CYNTHIA MCDONNELL                   Professor
    ## 495                           CARLSSON,ERIC                    Lecturer
    ## 496                        CARNE,DANIELLE L          Adjunct Instructor
    ## 497                              CARR,SUSAN         Clinical Instructor
    ## 498                     CARROLL,ALAN ROBERT                   Professor
    ## 499                          CARROLL,RACHEL                    Lecturer
    ## 500                        CARSTENSEN,PETER              Professor Emer
    ## 501                       CARTER,SARAH ANNE          Visiting Professor
    ## 502                      CASCIO,CHRISTOPHER         Assistant Professor
    ## 503                              CASID,JILL                   Professor
    ## 504                      CASIMIR,DAVID ALAN          Adjunct Instructor
    ## 505                         CASTRONOVO,RUSS                   Professor
    ## 506                          CATTAPAN,MOIRA         Clinical Instructor
    ## 507                       CATTAPAN,STEVEN E         Clinical Assoc Prof
    ## 508                         CAUL,KIMBERLY J         Clinical Assoc Prof
    ## 509                        CAVAGNERO,SILVIA                   Professor
    ## 510                         CAVINESS,JULIET         Clinical Instructor
    ## 511                 CEDERSTROM,B. MARCUS L.          Asst Faculty Assoc
    ## 512                            CENGIZ,PELIN       Assoc Professor (Chs)
    ## 513                       CENTOLA,MICHAEL J        Asst Prof Of Mil Sci
    ## 514                   CEREZO PAREDES,ALICIA         Associate Professor
    ## 515                              CERO,SHAUN        Asst Prof Of Mil Sci
    ## 516                         CERULLI,ANTHONY         Associate Professor
    ## 517                           CHACON,MARCUS       Assoc Professor (Chs)
    ## 518                   CHAIET,SCOTT RANDOLPH        Asst Professor (Chs)
    ## 519                  CHAMBERLAIN,CONNIE SUE         Associate Scientist
    ## 520            CHAMBERS,ANTHONY CHRISTOPHER             Senior Lecturer
    ## 521                       CHAMEDES,GIULIANA         Associate Professor
    ## 522                             CHAN,STELLA                    Lecturer
    ## 523                             CHANA,NADIA         Assistant Professor
    ## 524                            CHANCE,RON L           Faculty Associate
    ## 525                            CHANDA,BARON       Honorary Assoc/Fellow
    ## 526                       CHANDARANA,SHARAD             Senior Lecturer
    ## 527                           CHANDLER,BRAD           Faculty Associate
    ## 528                            CHANG,BRIANA         Associate Professor
    ## 529                               CHANG,HAO         Assistant Professor
    ## 530                              CHANG,LIZA          Research Associate
    ## 531                             CHANG,QIANG                   Professor
    ## 532                           CHANG,YU-CHAN          Visiting Asst Prof
    ## 533                        CHAPMAN,EDWIN R.                   Professor
    ## 534                CHAPMAN,ELIZABETH NICOLE          Clinical Asst Prof
    ## 535                     CHAPPELL,RICHARD J.                   Professor
    ## 536                        CHARLES,PAJARITA         Assistant Professor
    ## 537                              CHARO,ALTA                   Professor
    ## 538                        CHATTERJEE,RAHUL         Assistant Professor
    ## 539                            CHATTI,LEILA         Assoc Faculty Assoc
    ## 540                        CHAVAS,JEAN-PAUL                   Professor
    ## 541                           CHAVEZ,MONIKA                   Professor
    ## 542                 CHAVEZ-CONTRERAS,RAFAEL                Dis Lecturer
    ## 543                           CHAWLA,SHUCHI                   Professor
    ## 544                         CHEADLE,MICHAEL             Senior Lecturer
    ## 545                                CHEN,GAO         Assistant Professor
    ## 546                         CHEN,GUANG-HONG                   Professor
    ## 547                            CHEN,GUANHUA         Assistant Professor
    ## 548                           CHEN,HUI-CHUN                    Lecturer
    ## 549                            CHEN,KAIPING         Assistant Professor
    ## 550                             CHEN,LIANYI         Assistant Professor
    ## 551                                CHEN,NAN         Assistant Professor
    ## 552                          CHENEY,SCOTT B        Professor Of Mil Sci
    ## 553                           CHENG,CINDY I                   Professor
    ## 554                          CHEONG,YEONHEE                    Lecturer
    ## 555                      CHERWIN,KARIE LYNN              Assoc Lecturer
    ## 556                           CHESLER,NAOMI                   Professor
    ## 557                          CHEWNING,BETTY                   Professor
    ## 558                         CHIANG,HAROLD D         Assistant Professor
    ## 559                             CHIEN,PETER                   Professor
    ## 560                      CHILDERS,MICHAEL R                   Professor
    ## 561                         CHINN,MENZIE D.                   Professor
    ## 562                            CHINN,SEDONA         Assistant Professor
    ## 563                          CHISHOLM,SALLY                   Professor
    ## 564                               CHIU,BILL                   Professor
    ## 565                               CHO,JACEE         Assistant Professor
    ## 566                        CHOI,CHRISTOPHER                   Professor
    ## 567                        CHOI,KYOUNG-SHIN                   Professor
    ## 568                             CHOI,WILLIE         Associate Professor
    ## 569                           CHOPRA,PREETI                   Professor
    ## 570                     CHOQUETTE,MATTHEW P       Assoc Prof Of Mil Sci
    ## 571                          CHOWDHARY,ZARA              Assoc Lecturer
    ## 572                           CHOY,JENNIFER         Assistant Professor
    ## 573                              CHOY,PEGGY         Associate Professor
    ## 574                       CHRISTENSEN,CRAIG          Adjunct Instructor
    ## 575                     CHRISTENSON,BRIDGET                    Lecturer
    ## 576                CHRISTIAN,BRADLEY THOMAS                   Professor
    ## 577                  CHRISTOPHERSON,MELISSA         Assoc Faculty Assoc
    ## 578                      CHRISTY,KATHERYN R         Assistant Professor
    ## 579                           CHUI,MICHELLE                   Professor
    ## 580                              CHUN,JI NA         Assistant Professor
    ## 581                           CHUN,RUTHANNE          Clinical Professor
    ## 582                          CHUNG,DANIEL J                   Professor
    ## 583                             CHUNG,KEVIN         Assistant Professor
    ## 584                             CHUNG,MOO K         Associate Professor
    ## 585                         CHYLLA,SAMANTHA              Assoc Lecturer
    ## 586                         CIANCIA,KATHRYN         Associate Professor
    ## 587                          CIRELLI,CHIARA                   Professor
    ## 588                        CIRUZZI,DOMINICK              Assoc Lecturer
    ## 589                             CISLER,JOSH         Associate Professor
    ## 590                         CIUCCI,MICHELLE         Associate Professor
    ## 591                         CLAESSENS,AMY E         Associate Professor
    ## 592                    CLARK,HEIDI JENNIFER                    Lecturer
    ## 593                              CLARK,JOEL                    Lecturer
    ## 594                       CLARK,LAURIE BETH                   Professor
    ## 595                           CLARK,LINDSAY         Assistant Professor
    ## 596                          CLARK,ROSEANNE                   Professor
    ## 597                             CLARK,SHARI           Faculty Associate
    ## 598                              CLARK,TERI                    Lecturer
    ## 599                    CLARK-PUJARA,CHRISTY         Associate Professor
    ## 600                    CLARKE,LORELEI LYNNE          Clinical Asst Prof
    ## 601                      CLATTERBUCK,HAYLEY         Assistant Professor
    ## 602                               CLAUS,JIM                   Professor
    ## 603                      CLAUSS,ARRIETTA W.           Faculty Associate
    ## 604                         CLAYTON,SARAH C         Associate Professor
    ## 605                           CLOSE,GLEN S.                   Professor
    ## 606                         COBEY,COLLEEN E           Faculty Associate
    ## 607                         COBIAN,DANIEL G        Asst Professor (Chs)
    ## 608                          COBURN,JESSICA          Clinical Asst Prof
    ## 609                             COCHRAN,AMY         Assistant Professor
    ## 610                 CODLYN,ROCHELLE ALLEXIA         Clinical Instructor
    ## 611                             CODNER,ERIC         Assoc Faculty Assoc
    ## 612                           CODY,PAULA JO       Assoc Professor (Chs)
    ## 613                         COE,CHRISTOPHER                   Professor
    ## 614                       COENEN,JAN WILLEM           Adjunct Professor
    ## 615                               COFF,RUSS                   Professor
    ## 616                            COFFEY,PATTI           Faculty Associate
    ## 617                  COHEN,ADRIAN NATHANIEL          Adjunct Instructor
    ## 618                             COHEN,STACY         Clinical Assoc Prof
    ## 619                       COLE,JUSTIN DAVID         Assoc Faculty Assoc
    ## 620                     COLEMAN,FRANCISKA A         Assistant Professor
    ## 621                            COLLIER,LARA         Associate Professor
    ## 622                    COLLINS,ELIZABETH A.         Clinical Instructor
    ## 623                      COLLINS,J. MICHAEL                   Professor
    ## 624                         COLLINS,JANE L.                   Professor
    ## 625                       COLLINS,MARY BETH                    Lecturer
    ## 626                         COLLINS,MICHAEL              Professor Emer
    ## 627                      COLLINS,SUSAN LYNN          Adjunct Instructor
    ## 628                       COLMAN,RICKI JEAN         Assistant Professor
    ## 629                             COLOPY,SARA          Clinical Asst Prof
    ## 630                           COLQUHOUN,JED                   Professor
    ## 631                          COLUMNA,LUIS A         Associate Professor
    ## 632                             COMBS,DAVID                   Professor
    ## 633                 CONAWAY,JESSICA DEBORAH         Assoc Faculty Assoc
    ## 634                            CONLEY,SHAWN                   Professor
    ## 635                          CONN,AUDREY M.         Clinical Assoc Prof
    ## 636                    CONNER,CRAIG PATRICK           Adjunct Asst Prof
    ## 637                           CONNOR,NADINE                   Professor
    ## 638                             CONRAD,CLIF                   Professor
    ## 639                          CONROY,COLLEEN         Assistant Professor
    ## 640                            CONROY,TESSA         Assistant Professor
    ## 641                            CONTI,JOSEPH         Associate Professor
    ## 642                           CONWAY,KELLEY                   Professor
    ## 643                        CONWELL,JORDAN A         Assistant Professor
    ## 644                             COOK,DANE B                   Professor
    ## 645                            COOK,NIGEL B                   Professor
    ## 646                              COOK,SUSAN                   Professor
    ## 647                       COOK,THOMAS DAVID             Professor (Chs)
    ## 648                           COON,JOSHUA J                   Professor
    ## 649                              COON,KERRI         Assistant Professor
    ## 650                             COOPER,LISA                   Professor
    ## 651                            COPA,ANNETTE                    Lecturer
    ## 652                        COPELOVITCH,MARK                   Professor
    ## 653                    COPPAGE ARANDA,KEIVA                    Lecturer
    ## 654                       COPPERSMITH,SUSAN                   Professor
    ## 655                             CORBAE,DEAN                   Professor
    ## 656                              CORBY,KATE                   Professor
    ## 657                     COREY,DANIEL JOSEPH          Visiting Asst Prof
    ## 658                           CORFIS,IVY A.                   Professor
    ## 659                 CORNELIUS,DANIEL JOSEPH                    Lecturer
    ## 660                     COSTANZO,ERIN SUSAN             Professor (Chs)
    ## 661                     COTTER,MEGHAN MARIE                    Lecturer
    ## 662                            COUET,ADRIEN         Assistant Professor
    ## 663                 COURTIER,ANNA M. BISHOP         Assoc Faculty Assoc
    ## 664                       COVALESKI,MARK A.                   Professor
    ## 665             COVINGTON,ALEXANDER MICHAEL              Assoc Lecturer
    ## 666                   COVINGTON,ELIZABETH E           Faculty Associate
    ## 667                         COWAN,EILEEN A.        Asst Professor (Chs)
    ## 668                          COX,MICHAEL M.                   Professor
    ## 669                             COXHEAD,IAN                   Professor
    ## 670                             COYLE,SCOTT         Assistant Professor
    ## 671                             COYNE,SARAH          Adjunct Instructor
    ## 672                           CRABB,RICHARD                    Lecturer
    ## 673                        CRACIUN,GHEORGHE                   Professor
    ## 674                       CRAIG,ELIZABETH A                   Professor
    ## 675                      CRAIG,RACHEL DANAE          Clinical Asst Prof
    ## 676                             CRALL,JAMES         Assistant Professor
    ## 677                   CRAMER,KATHERINE JEAN                   Professor
    ## 678                           CRAMER,STEVEN                   Professor
    ## 679                           CRAVEN,MARK W                   Professor
    ## 680                     CRAWFORD,LATASHA K.         Assistant Professor
    ## 681                            CRENSHAW,TOM                   Professor
    ## 682                              CRIM,ELTON          Clinical Professor
    ## 683                             CRONE,WENDY                   Professor
    ## 684                          CRONON,WILLIAM       Honorary Assoc/Fellow
    ## 685                             CROOK,DAVID                   Professor
    ## 686                            CROSS,LORI J                    Lecturer
    ## 687                         CROWTHER,SHAUNA             Senior Lecturer
    ## 688                   CRUICKSHANKS,KAREN J.                   Professor
    ## 689                           CRYNS,VINCENT                   Professor
    ## 690                 CULBERSON,WESLEY STUART       Assoc Professor (Chs)
    ## 691                    CULLINANE,MICHAEL M.       Dis Faculty Associate
    ## 692                            CULP,LINDSEY         Clinical Instructor
    ## 693                         CULVER,KATHLEEN         Associate Professor
    ## 694                      CUNSOLO,ALESSANDRO              Assoc Lecturer
    ## 695                          CURRIE,CAMERON                   Professor
    ## 696                               CURRY,TOM           Faculty Associate
    ## 697                          CURTIN,JOHN J.                   Professor
    ## 698                      CURTIS,KATHERINE J                   Professor
    ## 699                       CUTSFORTH,TANYA M        Instructl Prg Mgr Ii
    ## 700                   CZAJKOWSKI,CYNTHIA M.                   Professor
    ## 701               CZUPRYNSKI,CHARLES JOSEPH                   Professor
    ## 702                               DAHL,GARY         Assoc Faculty Assoc
    ## 703                          DAHLKE,KATELYN          Asst Faculty Assoc
    ## 704                                 DAI,JUN         Assistant Professor
    ## 705                             DAKES,CHRIS           Faculty Associate
    ## 706                             DALE,THOMAS                   Professor
    ## 707                          DAMSCHEN,ELLEN                   Professor
    ## 708                           DANAHER,DAVID                   Professor
    ## 709                            DANKO,ISTVAN             Professor (Chs)
    ## 710                           DANTONI,LORIS         Assistant Professor
    ## 711                           DASU,SRIDHARA                   Professor
    ## 712                      DAVIDSON,RICHARD J                   Professor
    ## 713                   DAVIS,ABIGAIL NANETTE           Adjunct Professor
    ## 714                         DAVIS,DAWN BELT         Associate Professor
    ## 715                           DAVIS,ELISE C                    Lecturer
    ## 716                               DAVIS,JIM                   Professor
    ## 717                             DAVIS,SARAH          Clinical Professor
    ## 718                           DAVIS,THULANI         Assistant Professor
    ## 719                          DAVOODI,AZADEH                   Professor
    ## 720                            DAWSON,JULIE         Associate Professor
    ## 721                  DE FERRARI,GUILLERMINA                   Professor
    ## 722                        DE GASPERI,DIEGO         Clinical Instructor
    ## 723                   DE LEON GATTI,NATALIA                   Professor
    ## 724                    DE VILLIERS,MELGARDT             Professor (Chs)
    ## 725                    DE WERD,LARRY ALBERT                   Professor
    ## 726                          DE WITT,JOHN R             Senior Lecturer
    ## 727                               DEAN,DOUG         Assistant Professor
    ## 728                               DEAN,JAKE           Faculty Associate
    ## 729                      DEBAISIEUX,MARTINE                   Professor
    ## 730                        DEBOER,DOUGLAS J                   Professor
    ## 731                            DECI,DAVID M       Assoc Professor (Chs)
    ## 732                   DECICCO,MICHAEL PETER          Asst Faculty Assoc
    ## 733                            DECROIX,GREG                   Professor
    ## 734                              DEITZ,RITT           Faculty Associate
    ## 735                         DEL PIA,ALBERTO         Associate Professor
    ## 736                        DELANNAY,MARTINE       Sr Student Serv Coord
    ## 737                  DELGADILLO,THERESA ANN                   Professor
    ## 738                           DELLER,STEVEN                   Professor
    ## 739                     DELSANDRO,ELIZABETH         Clinical Assoc Prof
    ## 740                        DELUCA,HECTOR F.              Professor Emer
    ## 741                     DEMARCO,CHRISTOPHER              Professor Emer
    ## 742                            DEMETS,CHUCK                   Professor
    ## 743                         DEMETS,DAVID L.                   Professor
    ## 744                      DEMING,DUSTIN ALAN         Associate Professor
    ## 745                          DEMIRALP,ILHAN                    Lecturer
    ## 746                       DEMPSEY,ROBERT J.                   Professor
    ## 747                       DEMURI,GREGORY P.             Professor (Chs)
    ## 748                     DEN HARTOG,DANIEL J               Dis Scientist
    ## 749               DENECKERE,RAYMOND JACQUES                   Professor
    ## 750                           DENG,QUANLING          Visiting Asst Prof
    ## 751                           DENG,YONGHENG                   Professor
    ## 752                        DENISSOV,SERGUEI                   Professor
    ## 753                      DENNIS JR,SAMUEL F                   Professor
    ## 754                           DENNIS,JOSEPH         Associate Professor
    ## 755                            DENNIS,SHAWN                    Lecturer
    ## 756                         DENT,ERIK WOLFE                   Professor
    ## 757                             DENU,JOHN M                   Professor
    ## 758                          DEPPELER,DEBRA           Faculty Associate
    ## 759                           DESAI,ANKUR R                   Professor
    ## 760                              DESAI,ANUJ                   Professor
    ## 761                           DESAN,SUZANNE                   Professor
    ## 762                      DESHPANDE,ABBISHEK          Visiting Asst Prof
    ## 763                       DETCHEVERRY,CHARO                   Professor
    ## 764                        DETWYLER,ANATOLY         Assistant Professor
    ## 765                   DEVINE,PATRICIA GRACE                   Professor
    ## 766                       DEVOSS,AMANDA KAY         Clinical Instructor
    ## 767                             DEWANE,JUDY       Assoc Professor (Chs)
    ## 768                             DEWEY,COLIN                   Professor
    ## 769                               DEY,MAHUA         Assistant Professor
    ## 770                       DHARWADKER,APARNA                   Professor
    ## 771                        DHARWADKER,VINAY                   Professor
    ## 772                      DIAKONIKOLAS,ILIAS         Associate Professor
    ## 773                     DIAKONIKOLAS,JELENA         Assistant Professor
    ## 774                         DIAMOND,CAROL A       Assoc Professor (Chs)
    ## 775                          DIAMOND,JOHN B                   Professor
    ## 776                  DIAS MOREIRA,ANA SOFIA         Post Grad Trainee 5
    ## 777                         DICKMANN,LESLIE         Assoc Faculty Assoc
    ## 778                DIEM,STEPHANIE JOSEPHINE         Assistant Professor
    ## 779                         DIESTELMANN,MEG          Asst Faculty Assoc
    ## 780                      DIETZ,AMY TRENTHAM                   Professor
    ## 781                          DIFFEE,GARY M.                   Professor
    ## 782                          DIGMAN,MATTHEW         Assistant Professor
    ## 783                            DILL,CHARLES                   Professor
    ## 784                          DILLARD,JOSEPH                   Professor
    ## 785                    DILWORTH-BART,JANEAN                   Professor
    ## 786                               DIMA,VLAD                   Professor
    ## 787                               DINH,HONG           Faculty Associate
    ## 788                              DINH,HUY Q         Assistant Professor
    ## 789                            DIORIO,CHRIS                    Lecturer
    ## 790                      DIPRETE BROWN,LORI       Dis Faculty Associate
    ## 791                            DIRAN,INGRID         Assistant Professor
    ## 792                         DISANZA,ANTHONY                   Professor
    ## 793                               DOAN,AN H                   Professor
    ## 794                             DOBBS,TERYL                   Professor
    ## 795                   DODGE FRANCIS,CAROLEE                   Professor
    ## 796                            DOEBLEY,JOHN                   Professor
    ## 797                        DOESCHER,MICHAEL         Assoc Faculty Assoc
    ## 798                             DOING,JAMES                   Professor
    ## 799                  DOMINGUEZ,PETER JOSEPH                   Professor
    ## 800                         DOMINGUEZ,SUSAN             Senior Lecturer
    ## 801                            DONG,FENGXIA                    Lecturer
    ## 802                                DONG,WEI                   Professor
    ## 803                           DONGHIA,ELENA         Associate Professor
    ## 804                      DONNETT,URI BARUCH         Clinical Instructor
    ## 805                             DONOHUE,TIM                   Professor
    ## 806                           DOPFER,DOERTE         Associate Professor
    ## 807                               DOPP,JOHN       Assoc Professor (Chs)
    ## 808                            DOREN,BONNIE         Associate Professor
    ## 809                        DORO,CHRISTOPHER          Clinical Asst Prof
    ## 810                            DOSS,GRAYSON          Clinical Asst Prof
    ## 811                      DOUGLAS,JON CALVIN         Clinical Assoc Prof
    ## 812                              DOWER,PAUL         Assistant Professor
    ## 813                             DOWNEY,GREG                   Professor
    ## 814                  DOYLE JR.,JAMES EDWARD          Adjunct Assoc Prof
    ## 815                             DRAKE,DAVID                   Professor
    ## 816                          DRAKE,JENNIFER         Clinical Instructor
    ## 817                      DRESSER,LAURA JILL          Clinical Asst Prof
    ## 818                           DRESSLER,ALEX         Associate Professor
    ## 819                      DRESSLER,KRISTOFER                    Lecturer
    ## 820                         DREWAL,HENRY J.                   Professor
    ## 821                          DREWRY,JESSICA         Assoc Faculty Assoc
    ## 822            DRUSCHKE,CAROLINE GOTTSCHALK         Associate Professor
    ## 823                              DU,SHELDON         Associate Professor
    ## 824                           DUBOIS,THOMAS                   Professor
    ## 825                           DUELL,THERESA         Associate Professor
    ## 826                       DUERST,BARBARA L.           Faculty Associate
    ## 827                      DUFFY,SEAN MICHAEL        Asst Professor (Chs)
    ## 828                          DUGAN,HILARY A         Assistant Professor
    ## 829                           DUMESIC,JAMES              Professor Emer
    ## 830                           DUNCAN,IAN D.                   Professor
    ## 831                     DUNCAN,JEANNE MARIE           Faculty Associate
    ## 832                       DUNCAN,LARISSA G.         Associate Professor
    ## 833                        DUNHAM,RANDALL B              Professor Emer
    ## 834                            DUNN,JACOB T         Assoc Faculty Assoc
    ## 835                          DUNN,RACHEL M.                    Lecturer
    ## 836                            DUNNE,JOHN D                   Professor
    ## 837                  DURKIN,MAUREEN SUZANNE                   Professor
    ## 838               DURRANCE,CHRISTINE PIETTE         Associate Professor
    ## 839                     DUSICK,ALLISON FRAN         Clinical Instructor
    ## 840                           DUTTON,ANDREA                   Professor
    ## 841                      DWYER,DAVID EDWARD         Clinical Assoc Prof
    ## 842                    DYKEMA,JENNIFER LYNN         Visiting Assoc Prof
    ## 843                    DYKMAN,CHARLES PIPER          Adjunct Instructor
    ## 844                     DYMARZ,TULLIA MARIA         Associate Professor
    ## 845                             EADIE,LOREN         Assoc Faculty Assoc
    ## 846                           EASLAND,HOLLY                    Lecturer
    ## 847                              EASON,JOHN         Associate Professor
    ## 848                             EASWAR,VIJI         Assistant Professor
    ## 849                         EATON,CARRIE A.         Sr Academic Curator
    ## 850                       EATON,JOSHUA SETH          Clinical Asst Prof
    ## 851                      EBERT,STEVEN CAREY          Clinical Professor
    ## 852                            ECKHARDT,JON         Associate Professor
    ## 853                   ECKHARDT,LEE LOCHBAUM         Associate Professor
    ## 854                              EDGAR,MARK                    Lecturer
    ## 855                            EDGE,HEATHER                    Lecturer
    ## 856                          EDGERTON,LARRY           Faculty Associate
    ## 857                           EDIGER,MARK D                   Professor
    ## 858                      EDMONDS,BRITTNEY M         Assistant Professor
    ## 859                     EDORO,AINEHI EJIEME         Assistant Professor
    ## 860                           EDWARDS,COREY        Instrumentation Tech
    ## 861                         EDWARDS,DOROTHY                   Professor
    ## 862                            EDWARDS,GREG           Faculty Associate
    ## 863                           EDWARDS,LOGAN              Assoc Prof L/I
    ## 864                          EDWARDS,MORGAN         Assistant Professor
    ## 865                   EDWARDS,TIMOTHY DAVID          Adjunct Instructor
    ## 866                           EGAN,PATRICIA             Senior Lecturer
    ## 867                             EGEA,JUAN F                   Professor
    ## 868                              EGEDAL,JAN                   Professor
    ## 869                              EGGERT,TOM           Faculty Associate
    ## 870                     EHLENBACH,MARY LYNN       Assoc Professor (Chs)
    ## 871                     EHRENTHAL,DEBORAH B                   Professor
    ## 872                         EHRLICH,DAVID E         Assistant Professor
    ## 873                       EICHELMAN,BURR S.             Professor (Chs)
    ## 874                              EIDE,DAVID                   Professor
    ## 875                    EIRING,KRISTINE MARY                    Lecturer
    ## 876                         EISENSTEIN,RICK                   Professor
    ## 877                             EITH,ALYSON          Clinical Professor
    ## 878                           EITZER,ANDREW         Clinical Instructor
    ## 879                            EKLUND,KATIE         Associate Professor
    ## 880                       EL-NOSSERY,NEVINE         Associate Professor
    ## 881              ELDRIDGE,HANNAH VANDEGRIFT         Associate Professor
    ## 882                     ELDRIDGE,MARLOWE W.                   Professor
    ## 883                           ELDRIDGE,MARY              Assoc Lecturer
    ## 884                       ELFENBEIN,JOHANNA         Assistant Professor
    ## 885                  ELICEIRI,KEVIN WILLIAM         Associate Professor
    ## 886                        ELKHOULY,MOHAMED          Visiting Asst Prof
    ## 887                        ELLENBERG,JORDAN                   Professor
    ## 888                           ELLINGER,LISA              Assoc Lecturer
    ## 889                     ELLIS WEISMER,SUSAN                   Professor
    ## 890                              ELLIS,LISA             Senior Lecturer
    ## 891                          ELLISON,AUBREY          Asst Faculty Assoc
    ## 892                     ELLISON,PAUL ANDREW         Assistant Professor
    ## 893                     ELLISON,SHELBY LYNN         Assistant Professor
    ## 894                    ELSMO,ELIZABETH JANE          Clinical Asst Prof
    ## 895                            ELWERT,FELIX                   Professor
    ## 896                         EMBORG,MARINA E                   Professor
    ## 897                       EMIRBAYER,MUSTAFA                   Professor
    ## 898                          EMSHWILLER,EVE         Associate Professor
    ## 899                        ENDELMAN,JEFFREY         Associate Professor
    ## 900                          ENDERLE,GORDON           Faculty Associate
    ## 901                    ENDICOTT,SARAH ELISA          Clinical Professor
    ## 902                  ENDRES,MATTHEW CHARLES           Faculty Associate
    ## 903                           ENGEL,CHARLES                   Professor
    ## 904                      ENGELMAN,CORINNE D                   Professor
    ## 905                         ENGELMAN,MICHAL         Associate Professor
    ## 906                      ENGIN,FEYZA SONIYE         Assistant Professor
    ## 907                          ENGLAND,SAMUEL         Associate Professor
    ## 908                        ENGLE,JONATHAN W         Assistant Professor
    ## 909                               ENKE,FINN                   Professor
    ## 910                       ENRIGHT,ROBERT D.                   Professor
    ## 911                         ENRIQUEZ,FALINA         Assistant Professor
    ## 912                             ENSOR,SARAH         Assistant Professor
    ## 913                              ENSTAD,NAN                   Professor
    ## 914                          EOM,CHANG-BEOM                   Professor
    ## 915                               EPP,AMBER         Associate Professor
    ## 916                             EPP,RUSSELL             Senior Lecturer
    ## 917                            EPPLI,MARK J           Faculty Associate
    ## 918                            ERAKER,BJORN                   Professor
    ## 919                       ERBIL ERKAN,NALAN          Asst Faculty Assoc
    ## 920                      ERIKSSON,MARK ALAN                   Professor
    ## 921                            ERITEN,MELIH         Associate Professor
    ## 922                           ERKER,TEDWARD          Asst Faculty Assoc
    ## 923                         ERLANGER,HOWARD                   Professor
    ## 924                           ERMAKOFF,IVAN                   Professor
    ## 925                          ERMAN,DANIEL M         Associate Professor
    ## 926                              ERSIG,ANNE         Assistant Professor
    ## 927                    ESCHENFELDER,KRISTIN                   Professor
    ## 928                     ESCOTT-STUMP,SYLVIA         Assoc Faculty Assoc
    ## 929                            ESKOLA,LIANA          Clinical Asst Prof
    ## 930                     ESSELMAN,BRIAN JOHN           Faculty Associate
    ## 931                              ETZEL,MARK                   Professor
    ## 932                              EUDEY,GWEN             Senior Lecturer
    ## 933                        EVANS,DAVID TODD                   Professor
    ## 934                             EVANS,HEIDI           Faculty Associate
    ## 935                           EVANS,PAUL G.                   Professor
    ## 936                     EVANS-ROMAINE,KAREN                   Professor
    ## 937                   EVENSEN,ANN ELIZABETH             Professor (Chs)
    ## 938                          EVERETT,LISA L                   Professor
    ## 939                         FABRY,ZSUZSANNA                   Professor
    ## 940                            FAHL,WILLIAM                   Professor
    ## 941                      FAHY,JENNIFER LYNN                    Lecturer
    ## 942                     FAIN,SEAN BEDILLION                   Professor
    ## 943                      FALK,KATHLEEN MARY           Faculty Associate
    ## 944                     FALK,MICHAEL EDWARD           Adjunct Professor
    ## 945                       FAMAKIN,BOLANLE M         Assistant Professor
    ## 946                                FAN,JING         Assistant Professor
    ## 947                             FAN,SHUXING         Assistant Professor
    ## 948                            FANG,HANLONG          Visiting Asst Prof
    ## 949                                 FANG,KE         Assistant Professor
    ## 950                          FARHAT,WALID A             Professor (Chs)
    ## 951                          FAUST,JENNIFER                    Lecturer
    ## 952                            FAWAZ,KASSEM         Assistant Professor
    ## 953                             FAWAZ,RAMZI         Associate Professor
    ## 954                          FEDENIA,LAUREN                    Lecturer
    ## 955                         FEDENIA,MARK A.         Associate Professor
    ## 956                              FEIGL,KURT                   Professor
    ## 957                    FEINSTEIN,NOAH WEETH         Associate Professor
    ## 958                         FELDMAN,MIKHAIL                   Professor
    ## 959                    FELDSTEIN,DAVID ALAN             Professor (Chs)
    ## 960                        FELTON,ELIZABETH        Asst Professor (Chs)
    ## 961                              FENG,DAWEI         Assistant Professor
    ## 962                                FENG,IVY         Assistant Professor
    ## 963             FERGUSON,JEANNE MARIE BYRON                    Lecturer
    ## 964                      FERNANDES,EARLENCE         Assistant Professor
    ## 965                         FERNANDEZ,DONNA                   Professor
    ## 966                         FERRARETTO,LUIZ         Assistant Professor
    ## 967                        FERREE,MYRA MARX       Honorary Assoc/Fellow
    ## 968              FERREIRA,TATIANA HENRIQUES          Clinical Asst Prof
    ## 969                             FERRIER,KEN         Assistant Professor
    ## 970                          FERRIS,MICHAEL                   Professor
    ## 971              FIEGEL-NEWLON,JENNIFER ANN         Clinical Assoc Prof
    ## 972                             FIELD,AMBER              Assoc Lecturer
    ## 973                        FIELDER,BRIGITTE         Associate Professor
    ## 974                             FIELDS,BETH         Assistant Professor
    ## 975                            FIELDS,DAVID          Asst Faculty Assoc
    ## 976                           FINDLEY,KEITH                   Professor
    ## 977                   FINLEY,KATHRYN BELLIS          Clinical Asst Prof
    ## 978                            FINNEY,MISHA         Assoc Faculty Assoc
    ## 979                        FIORENZA,MARY E.           Faculty Associate
    ## 980                        FISCHER,COLLETTE                    Lecturer
    ## 981                           FISCHER,ISMOR             Senior Lecturer
    ## 982                          FISCHER,MARTHA                   Professor
    ## 983                            FISH,JEFFREY         Clinical Instructor
    ## 984                    FISHER,MADELINE MARY           Faculty Associate
    ## 985                         FISHLER,THERESA          Asst Faculty Assoc
    ## 986                 FITZPATRICK,MEGAN BURKE        Asst Professor (Chs)
    ## 987                        FITZSIMONS,SARAH         Assistant Professor
    ## 988                      FLANAGAN,CONSTANCE                   Professor
    ## 989                   FLANARY,PETER WILLIAM                    Lecturer
    ## 990                          FLETCHER,EMILY         Associate Professor
    ## 991                        FLETCHER,JASON M                   Professor
    ## 992                              FLUGA,ERIC           Adjunct Asst Prof
    ## 993                  FLYNN,MAXFIELD PATRICK        Asst Professor (Chs)
    ## 994                            FOLTZ,JEREMY                   Professor
    ## 995                      FONCK,RAYMOND JOHN              Professor Emer
    ## 996                   FONDOW,STEVEN RICHARD         Assoc Faculty Assoc
    ## 997                        FORD II,JAMES H.         Assistant Professor
    ## 998                             FOREST,CARY                   Professor
    ## 999                       FOREST,KATRINA T.                   Professor
    ## 1000                        FORREST,LISA J.                   Professor
    ## 1001                 FORSTER BENEDICT,STACY           Faculty Associate
    ## 1002                            FOST,NORMAN              Professor Emer
    ## 1003                       FOWLER,AMY MARIE         Assistant Professor
    ## 1004                         FOWLER,CYNTHIA                   Professor
    ## 1005                         FOX,ASHBY KENT              Assoc Lecturer
    ## 1006                           FOX,BRIAN G.                   Professor
    ## 1007                        FOX,CATHERINE A                   Professor
    ## 1008                            FOYS,MARTIN                   Professor
    ## 1009                   FRANCETIC LEPE,LINDA           Faculty Associate
    ## 1010                FRANCHINO,DAVID CHARLES           Adjunct Asst Prof
    ## 1011                   FRANCIS,DAVID OLIVER         Associate Professor
    ## 1012                       FRANCK,CHRISTIAN         Associate Professor
    ## 1013                        FRANCK,JENNIFER         Assistant Professor
    ## 1014                          FRANCOIS,MARY          Clinical Asst Prof
    ## 1015                        FRANK,CHRISTINA                    Lecturer
    ## 1016                            FRANK,HEIDI         Assoc Faculty Assoc
    ## 1017                         FRANK,VICTORIA              Assoc Lecturer
    ## 1018                             FRANTZ,EVA         Clinical Instructor
    ## 1019                           FRATTA,DANTE         Associate Professor
    ## 1020                        FREDETTE,STEVEN         Assoc Faculty Assoc
    ## 1021                   FREDRICKSON,DANIEL C                   Professor
    ## 1022                           FREEDMAN,ZAC         Assistant Professor
    ## 1023                      FREELAND,ROBERT F                   Professor
    ## 1024                          FREEMAN,KATIE          Asst Faculty Assoc
    ## 1025                          FREID,MATTHEW                    Lecturer
    ## 1026                            FRICKE,PAUL                   Professor
    ## 1027                        FRIEDLAND,LEWIS                   Professor
    ## 1028                    FRIEDMAN,JAMES ALAN          Adjunct Instructor
    ## 1029                    FRIEDMAN,MATTHEW L.              Assoc Lecturer
    ## 1030                         FRIEDMAN,SUSAN                   Professor
    ## 1031                       FRIEDRICH,THOMAS                   Professor
    ## 1032                   FRIEDRICHS,KRISTEN R         Clinical Assoc Prof
    ## 1033                      FRIESEN,PAUL DEAN                   Professor
    ## 1034                  FRITSCH,MICHAEL KEVIN             Professor (Chs)
    ## 1035                  FROST,NICKOLAS DELMAR         Assistant Professor
    ## 1036                                FU,CHAO                   Professor
    ## 1037                              FU,SHUBIN          Visiting Asst Prof
    ## 1038                      FUHREMANN,KRISTEN           Faculty Associate
    ## 1039                          FUJIMURA,JOAN                   Professor
    ## 1040                           FULMER,MIMMI                   Professor
    ## 1041                           FULTON,SCOTT           Adjunct Professor
    ## 1042                            FUNK,LUKE M         Associate Professor
    ## 1043                          FURLONG,SCOTT              Assoc Lecturer
    ## 1044                         FURUMOTO,DAVID                   Professor
    ## 1045                           GABAI,JOSHUA              Assoc Lecturer
    ## 1046                            GABER,ALICE              Assoc Lecturer
    ## 1047                        GADDIS,JENNIFER         Assistant Professor
    ## 1048                     GADE,ANNA MARGARET                   Professor
    ## 1049                         GAERTNER,FABIO         Associate Professor
    ## 1050                       GAJESKI,SHARON K           Faculty Associate
    ## 1051                       GALIPEAU,JACQUES                   Professor
    ## 1052                  GALLAGHER,CATHERINE L             Professor (Chs)
    ## 1053                        GALLIMORE,CASEY       Assoc Professor (Chs)
    ## 1054                     GALLIMORE,JONATHAN             Senior Lecturer
    ## 1055                        GALMOZZI,ANDREA         Assistant Professor
    ## 1056                         GALVAO,LOREN W           Faculty Associate
    ## 1057                             GAMM,DAVID                   Professor
    ## 1058                      GAMMIE,STEPHEN C.                   Professor
    ## 1059                           GANCO,MARTIN         Associate Professor
    ## 1060                    GANGL,AMY ELIZABETH         Assoc Faculty Assoc
    ## 1061                            GANGNON,RON                   Professor
    ## 1062                        GANZ,OLGA RADKO         Assoc Faculty Assoc
    ## 1063                               GAO,SONG         Assistant Professor
    ## 1064                         GARAND,ETIENNE         Associate Professor
    ## 1065                           GARBACZ,ANDY         Associate Professor
    ## 1066                 GARCIA TRILLOS,NICOLAS         Assistant Professor
    ## 1067                       GARCIA,ALEXANDRA              Assoc Lecturer
    ## 1068                           GARCIA,DENIA         Assistant Professor
    ## 1069                            GAROON,JOSH         Assistant Professor
    ## 1070                      GARTLAND,SHARON G          Clinical Professor
    ## 1071                        GARTNER,WILLIAM             Senior Lecturer
    ## 1072                        GASCH,AUDREY P.                   Professor
    ## 1073                           GASPER,DAVID          Clinical Asst Prof
    ## 1074               GATHMAN,CABELL HANKINSON                    Lecturer
    ## 1075                        GATTENBY,TIM G.       Dis Faculty Associate
    ## 1076                      GAUDREAU,JOSEPH B               Professor L/I
    ## 1077                           GAVINS,JAMES                    Lecturer
    ## 1078                                GE,YING                   Professor
    ## 1079                            GEBBIE,MATT         Assistant Professor
    ## 1080                        GEIGER,BENEDIKT         Assistant Professor
    ## 1081                      GELLMAN,SAMUEL H.                   Professor
    ## 1082                   GENNERMAN,REBECCA JO         Clinical Instructor
    ## 1083                            GENSKOW,KEN                   Professor
    ## 1084                             GEORGE,MAY                    Lecturer
    ## 1085                   GEORGIADES,ARISTOTLE                   Professor
    ## 1086                            GERA,PRERNA          Visiting Asst Prof
    ## 1087                GERARD,HEATHER STEPHANY           Adjunct Professor
    ## 1088                           GERASSI,LARA         Assistant Professor
    ## 1089                     GERBER,THEODORE P.                   Professor
    ## 1090                          GERHART,BARRY                   Professor
    ## 1091                          GERN,JAMES E.                   Professor
    ## 1092                 GERNSBACHER,MORTON ANN                   Professor
    ## 1093                     GEVENS,AMANDA JANE                   Professor
    ## 1094                            GEYER,NAOMI         Associate Professor
    ## 1095                           GHANDHI,JAAL                   Professor
    ## 1096                        GHOUSSEINI,HALA         Associate Professor
    ## 1097                    GIBBS,HOLLY KRISTEN         Associate Professor
    ## 1098                          GIBSON,MARTHA           Faculty Associate
    ## 1099                      GICQUELAIS,RACHEL         Assistant Professor
    ## 1100                            GIDAL,BARRY             Professor (Chs)
    ## 1101                        GILBERT,LEWIS E             Senior Lecturer
    ## 1102                           GILBERT,PUPA                   Professor
    ## 1103                    GILLETT,JOHN ROBERT             Senior Lecturer
    ## 1104                       GILLIAN,ANNELYNN           Faculty Associate
    ## 1105                           GILLIE,NAZAN                    Lecturer
    ## 1106                 GILLIS,COLIN RADCLIFFE                    Lecturer
    ## 1107                       GILMORE,JANET C.       Honorary Assoc/Fellow
    ## 1108                           GILROY,SIMON                   Professor
    ## 1109                   GINDER-VOGEL,MATTHEW         Associate Professor
    ## 1110                      GIOIA,CHRISTOPHER         Clinical Assoc Prof
    ## 1111           GIOVANNELLI CAPUTO,CHRISTINA              Assoc Lecturer
    ## 1112                        GIPSON,JENNIFER         Assistant Professor
    ## 1113                         GITTER,ANTHONY         Assistant Professor
    ## 1114                      GIVNISH,THOMAS J.                   Professor
    ## 1115                     GLADSTONE,BRUCE E.             Senior Lecturer
    ## 1116                          GLASPIE,JODIE          Asst Faculty Assoc
    ## 1117                     GLAWTSCHEW,REBECCA                    Lecturer
    ## 1118                         GLAZER,JEFFREY         Clinical Assoc Prof
    ## 1119                       GLEICHER,MICHAEL                   Professor
    ## 1120                         GLINBERG,LANNY          Clinical Asst Prof
    ## 1121                      GLINSMANN,BETHANY         Assoc Faculty Assoc
    ## 1122                      GLORIA,ALBERTA M.                   Professor
    ## 1123                          GLOTZER,PAIGE         Assistant Professor
    ## 1124                       GLOWACKI,GULNARA             Senior Lecturer
    ## 1125                         GLUKHOV,ALEXEY         Assistant Professor
    ## 1126                         GOCMEN,ASLIGUL         Associate Professor
    ## 1127                         GODFREY,BROOKE          Asst Faculty Assoc
    ## 1128               GOETZINGER,MATTHEW JAMES                    Lecturer
    ## 1129                             GOFF,PETER         Assistant Professor
    ## 1130                             GOH,JUN LE          Visiting Asst Prof
    ## 1131                            GOLAB,HANNA              Assoc Lecturer
    ## 1132                     GOLDBERG,CHAD ALAN                   Professor
    ## 1133                         GOLDBERG,SIMON         Assistant Professor
    ## 1134                          GOLDBERG,TONY                   Professor
    ## 1135                     GOLDBERGER,ZACHARY       Assoc Professor (Chs)
    ## 1136                        GOLDEN,JENNIFER         Assistant Professor
    ## 1137                GOLDGEL-CARBALLO,VICTOR         Associate Professor
    ## 1138                          GOLDMAN,IRWIN                   Professor
    ## 1139                         GOLDSMITH,HILL                   Professor
    ## 1140                    GOLDSMITH,RANDALL H         Associate Professor
    ## 1141               GOLDSTEIN,RUTH ELIZABETH         Assistant Professor
    ## 1142                      GOLOS,THADDEUS G.                   Professor
    ## 1143                      GOMEZ,MARY LOUISE                   Professor
    ## 1144                            GOMEZ,PABLO         Associate Professor
    ## 1145                        GOMEZ,TIMOTHY M                   Professor
    ## 1146                            GONDI,VINAI  Clinical Adjunct Asst Prof
    ## 1147                     GONG,SHAOQIN SARAH                   Professor
    ## 1148                         GONG,XIANGHONG                   Professor
    ## 1149                     GONZALEZ,ALEXANDER          Asst Faculty Assoc
    ## 1150                           GOOD,ANNALEE                    Lecturer
    ## 1151                    GOODING,DIANE CAROL                   Professor
    ## 1152                        GOODKIN,RICHARD                   Professor
    ## 1153                       GOODWIN,LAUREL B                   Professor
    ## 1154                          GOPALAN,PADMA                   Professor
    ## 1155                            GORIN,VADIM         Associate Professor
    ## 1156                       GOSBEE,ALYSSA L.                    Lecturer
    ## 1157                         GOTTLIEB,PAULA                   Professor
    ## 1158                 GOTTWALD,JENNIFER ROSE           Adjunct Professor
    ## 1159                         GOURSE,RICHARD                   Professor
    ## 1160                         GRABOIS,DANIEL         Associate Professor
    ## 1161                           GRAEFE,GOETZ       Honorary Assoc/Fellow
    ## 1162                           GRAHAM,LINDA                   Professor
    ## 1163                            GRAHAM,MIKE                   Professor
    ## 1164                       GRAHAM,STEPHANIE          Clinical Professor
    ## 1165                       GRAINGER,CORBETT         Associate Professor
    ## 1166                        GRALNICK,LISA B                   Professor
    ## 1167                  GRANDE,KATARINA MARIA                    Lecturer
    ## 1168                         GRANICK,MARTIN         Clinical Instructor
    ## 1169                             GRANT,CARL                   Professor
    ## 1170                         GRANT,MONICA J         Associate Professor
    ## 1171                             GRANT,PAUL                    Lecturer
    ## 1172                          GRANT,TIMOTHY         Assistant Professor
    ## 1173                        GRATTON,CLAUDIO                   Professor
    ## 1174                             GRAUE,BETH                   Professor
    ## 1175                           GRAVES,LUCAS         Associate Professor
    ## 1176                           GRAVES,SARAH                    Lecturer
    ## 1177                          GRAY,JONATHAN                   Professor
    ## 1178                              GRECO,JIM           Faculty Associate
    ## 1179                         GREEN,C. SHAWN         Associate Professor
    ## 1180                    GREEN,CHELSEY MARIE              Assoc Lecturer
    ## 1181                 GREEN,TIFFANY LORRAINE         Assistant Professor
    ## 1182                       GREENBERG,ANDREW       Dis Faculty Associate
    ## 1183                       GREENE,CHRISTINA                   Professor
    ## 1184                           GREENE,LINDA                   Professor
    ## 1185                GREENE,MADELYNE ZUEHLKE         Assistant Professor
    ## 1186                  GREENWALD,MERCY MAXAN          Asst Faculty Assoc
    ## 1187                       GREENWOOD,PHILIP             Senior Lecturer
    ## 1188                   GREGORY,JESSE MCCUNE         Associate Professor
    ## 1189                             GREIG,TONY             Senior Lecturer
    ## 1190                   GRIEP,ANNE ELIZABETH                   Professor
    ## 1191                         GRIFFITH,EMILY         Associate Professor
    ## 1192                          GRIFFITH,MATT                    Lecturer
    ## 1193                            GRIMM,GERIT         Associate Professor
    ## 1194                      GRINBLAT,YEVGENYA         Associate Professor
    ## 1195                        GRIZZARD,ROBERT           Faculty Associate
    ## 1196                            GROB,RACHEL          Clinical Professor
    ## 1197                         GROBLEWSKI,GUY                   Professor
    ## 1198                           GRODSKY,ERIC                   Professor
    ## 1199                          GROSS,DOMINIC         Assistant Professor
    ## 1200                     GROSS,JOHN PATRICK         Clinical Assoc Prof
    ## 1201                    GROSS,KELSEY NICOLE          Asst Faculty Assoc
    ## 1202                           GROSS,SABINE                   Professor
    ## 1203                    GROSSENBACHER,LAURA           Faculty Associate
    ## 1204                         GROVES,RUSSELL                   Professor
    ## 1205                            GRUBEN,KREG                   Professor
    ## 1206                        GRUNEWALD,RALPH         Assistant Professor
    ## 1207                         GUBNER,JOHN A.                   Professor
    ## 1208                      GUEDOT,CHRISTELLE         Associate Professor
    ## 1209                     GUILLIAMS,THOMAS G          Adjunct Assoc Prof
    ## 1210                    GULLICKSON,MICHELLE                    Lecturer
    ## 1211                          GUMPERZ,JENNY                   Professor
    ## 1212                   GUNASEKARAN,SUNDARAM                   Professor
    ## 1213                          GUNNESON,ERIK           Faculty Associate
    ## 1214                           GUO,SHAOMING         Assistant Professor
    ## 1215                                GUO,WEI         Assistant Professor
    ## 1216                            GUO,XIAOQIN          Visiting Asst Prof
    ## 1217                            GUPTA,MOHIT         Assistant Professor
    ## 1218                           GUPTE,SACHIN         Clinical Instructor
    ## 1219                       GUREVICH,SHAMGAR         Associate Professor
    ## 1220                          GURNEE,KENDRA              Assoc Lecturer
    ## 1221                GUSSICK,MEGAN ELIZABETH          Clinical Asst Prof
    ## 1222                             GUSTIN,LEA         Assoc Faculty Assoc
    ## 1223                 GUTIERREZ CHACON,LUCIA         Associate Professor
    ## 1224                             GUYER,SARA                   Professor
    ## 1225                       HA,MELISSA ELLEN         Clinical Instructor
    ## 1226                         HAAS,CHRISTINE                    Lecturer
    ## 1227                              HAAS,NATE              Assoc Lecturer
    ## 1228                              HAAS,RUSS           Faculty Associate
    ## 1229                      HABECK,KODY LOUIS        Asst Instrmt Inn/Ins
    ## 1230                       HABERKORN,TYRELL                   Professor
    ## 1231                      HADEN,CLARE ARENA                    Lecturer
    ## 1232                       HADLEY,DOUGLAS B             Senior Lecturer
    ## 1233                        HAFEZ,GHOLAM R.             Professor (Chs)
    ## 1234                    HAGER,DAVID RICHARD          Clinical Asst Prof
    ## 1235                  HAGERICH,KIMBERLY ANN             Senior Lecturer
    ## 1236                   HAGERMOSER,ELIZABETH          Clinical Asst Prof
    ## 1237                          HAGNESS,SUSAN                   Professor
    ## 1238                     HAHN,ERIN MARGARET          Adjunct Instructor
    ## 1239                              HAI,AVIAD         Assistant Professor
    ## 1240                   HAIRSTON,MARK STEVEN         Assistant Professor
    ## 1241                       HALBACH,THEODORE         Assoc Faculty Assoc
    ## 1242                           HALBERG,RICH         Associate Professor
    ## 1243                             HALL,APRIL           Adjunct Asst Prof
    ## 1244                          HALL,DEANNE J          Adjunct Instructor
    ## 1245                             HALL,EMILY       Dis Faculty Associate
    ## 1246                              HALL,JOHN         Associate Professor
    ## 1247                       HALL,TIMOTHY JON                   Professor
    ## 1248                 HALLISY,KRISTINE MARIE       Assoc Professor (Chs)
    ## 1249                          HALLORAN,MARY                   Professor
    ## 1250                             HALM,WENDY         Clinical Assoc Prof
    ## 1251                   HALPERN-MEEKIN,SARAH         Associate Professor
    ## 1252                    HALVERSON,ALAN DALE          Adjunct Assoc Prof
    ## 1253                        HALVERSON,ERICA                   Professor
    ## 1254                HALVERSON,RICHARD ROGER                   Professor
    ## 1255                      HALZEN,FRANCIS L.                   Professor
    ## 1256                     HAMERS,ROBERT JOHN                   Professor
    ## 1257                     HAMPTON,JESSE CLAY         Assistant Professor
    ## 1258                  HAMPTON,JOHN MITCHELL                  Researcher
    ## 1259                                 HAN,LU                   Professor
    ## 1260                    HANDELSMAN,JO EMILY                   Professor
    ## 1261                      HANHART,ALEXANDER         Assoc Faculty Assoc
    ## 1262                            HANNA,AMGAD             Professor (Chs)
    ## 1263                             HANNA,AWAD                   Professor
    ## 1264                   HANNON,JENNIFER ANNE          Adjunct Instructor
    ## 1265                            HANSEN,ANNE                   Professor
    ## 1266                        HANSEN,BRUCE E.                   Professor
    ## 1267                           HANSEN,DAVID                    Lecturer
    ## 1268                 HANSEN,KAREN ELIZABETH                   Professor
    ## 1269                       HANSEN,KORINNA K             Senior Lecturer
    ## 1270                  HANSON BRENNER,GAIL M           Faculty Associate
    ## 1271                          HANSON,KAEL D                   Professor
    ## 1272                          HANSON,LANE L              Assoc Lecturer
    ## 1273                     HANSON,PAUL CONRAD                    Lecturer
    ## 1274                         HANUKAI,MAKSIM         Assistant Professor
    ## 1275                    HARACKIEWICZ,JUDITH                   Professor
    ## 1276                       HARDIE,ROBERT J.          Clinical Professor
    ## 1277                            HARDIN,JEFF                   Professor
    ## 1278                        HARER,MATTHEW W        Asst Professor (Chs)
    ## 1279                              HARK,MARY                   Professor
    ## 1280                    HAROLDSON,AMBER RAE         Assoc Faculty Assoc
    ## 1281                      HARRILL,STEPHANIE                    Lecturer
    ## 1282                        HARRINGTON,GREG                   Professor
    ## 1283                   HARRINGTON,JOHN ALAN                   Professor
    ## 1284                          HARRIS,ANDREA         Associate Professor
    ## 1285                        HARRIS,MICHELLE       Dis Faculty Associate
    ## 1286                          HARRIS,RONALD       Dis Faculty Associate
    ## 1287                       HARRISON,MELISSA         Associate Professor
    ## 1288                             HART,SARAH         Assistant Professor
    ## 1289                      HARTEL,RICHARD W.                   Professor
    ## 1290                       HARTEMINK,ALFRED                   Professor
    ## 1291                       HARTENBACH,ELLEN                   Professor
    ## 1292                HARTER,JOSEPHINE MIRIAM       Assoc Professor (Chs)
    ## 1293                          HARTLEY,SIGAN         Associate Professor
    ## 1294                            HARTMAN,AMY          Clinical Professor
    ## 1295                           HARTMAN,JEFF        Asst Professor (Chs)
    ## 1296                   HARTMAN,SCOTT AUSTIN          Asst Faculty Assoc
    ## 1297                    HARTUP,BARRY KINNEY         Clinical Instructor
    ## 1298                        HARVEY,MELODY A         Assistant Professor
    ## 1299                          HASHIMOTO,AKI                   Professor
    ## 1300                        HASSETT,DAWNENE                   Professor
    ## 1301                             HASTI,BECK           Faculty Associate
    ## 1302                      HASTINGS,PATRICIA       Dis Faculty Associate
    ## 1303                   HATLAN-ATWELL,HANNAH       Student Services Cord
    ## 1304                         HATZEL,JEFFREY                    Lecturer
    ## 1305                             HAUSCH,DON                   Professor
    ## 1306                          HAVEY,MICHAEL       Honorary Assoc/Fellow
    ## 1307                       HAWKINS,MARGARET                   Professor
    ## 1308                         HAWKINS,SHAWNA         Clinical Instructor
    ## 1309                             HAWKS,JOHN                   Professor
    ## 1310                         HAWLEY,DONNA J           Faculty Associate
    ## 1311                           HAWLEY,HELEN                    Lecturer
    ## 1312                           HAYATI,FAZEL                    Lecturer
    ## 1313                         HAYES,MORGAN M              Assoc Lecturer
    ## 1314           HAYNES MANOGUE,JONANNE MARIE                    Lecturer
    ## 1315                           HAYNES,APRIL         Associate Professor
    ## 1316                            HAYNEY,MARY             Professor (Chs)
    ## 1317                   HAYS,REBECCA ELEANOR              Assoc Lecturer
    ## 1318                           HAZEN,ALICIA                    Lecturer
    ## 1319                               HE,CHENG         Assistant Professor
    ## 1320                       HEALLESS,LINDSAY         Clinical Instructor
    ## 1321                         HEATON,CAITLIN         Clinical Instructor
    ## 1322                         HEFFNER,THOMAS             Senior Lecturer
    ## 1323                            HEGNA,CHRIS                   Professor
    ## 1324                            HEIDE,JAN B                   Professor
    ## 1325                      HEIDE,MARIA PAPAS             Senior Lecturer
    ## 1326                        HEIDEMAN,BRENDA              Assoc Lecturer
    ## 1327                     HEIDERSCHEIT,BRYAN                   Professor
    ## 1328                        HEIMERL,FLORIAN          Asst Faculty Assoc
    ## 1329                          HEIMKE,JEREMY        Asst Prof Of Mil Sci
    ## 1330                 HEINER,ELIZABETH ALLEN          Adjunct Instructor
    ## 1331                          HEINTZ,CLAUDE           Faculty Associate
    ## 1332                        HEINZ,SEBASTIAN                   Professor
    ## 1333                     HELD,PATRICE KARYN       Assoc Professor (Chs)
    ## 1334                         HEMATTI,PEIMAN                   Professor
    ## 1335                          HENAK,CORINNE         Assistant Professor
    ## 1336                     HENDERSON,DOUGLASS                   Professor
    ## 1337                 HENDERSON,MEGHAN MARIE              Assoc Lecturer
    ## 1338                     HENDERSON,SHERYL L       Assoc Professor (Chs)
    ## 1339                  HENDERSON,STEPHANIE A         Assistant Professor
    ## 1340                    HENDERSON,TY THOMAS         Visiting Assoc Prof
    ## 1341                        HENDLEY,KATHRYN                   Professor
    ## 1342                      HENDRICKS,KENNETH                   Professor
    ## 1343                            HENKE,JAMIE       Dis Faculty Associate
    ## 1344                             HENKE,RYAN         Assistant Professor
    ## 1345                     HENNESSY,ELIZABETH         Associate Professor
    ## 1346            HENNING,REBECCA LYNN WARNER          Clinical Asst Prof
    ## 1347                      HENRICHS,RACHEL M           Faculty Associate
    ## 1348                         HENRIQUES,JEFF                Dis Lecturer
    ## 1349                         HENRY,TRAVIS J           Adjunct Asst Prof
    ## 1350                   HENZLER,KATHERINE A.         Associate Professor
    ## 1351                           HEPLER,BRIAN          Visiting Asst Prof
    ## 1352                                 HER,PA          Clinical Asst Prof
    ## 1353                           HERMANN,MATT         Assoc Faculty Assoc
    ## 1354                            HERMANS,IVE                   Professor
    ## 1355                      HERNANDEZ,ANTONIO         Assoc Faculty Assoc
    ## 1356                        HERNANDEZ,LAURA         Associate Professor
    ## 1357                        HERNANDEZ,PAOLA                   Professor
    ## 1358                      HERNANDEZ,REINIER         Assistant Professor
    ## 1359                         HERNANDO,DIEGO         Assistant Professor
    ## 1360                      HERNDON,MATTHEW F                   Professor
    ## 1361                      HERNKE,MICHAEL T.                    Lecturer
    ## 1362                    HERRERA,KYLE JORDAN                    Lecturer
    ## 1363                        HERRERA,YOSHIKO                   Professor
    ## 1364                          HERRINGA,RYAN         Associate Professor
    ## 1365                 HERSHBERGER,KAREN LYNN                    Lecturer
    ## 1366                        HERSHEY,DAVID M         Assistant Professor
    ## 1367                           HERZOG,EMILY         Clinical Instructor
    ## 1368                    HERZOG,MELANIE ANNE             Senior Lecturer
    ## 1369                             HESS,ERICA              Assoc Lecturer
    ## 1370                             HESS,JAMIE       Assoc Professor (Chs)
    ## 1371                           HETZLER,MARK                   Professor
    ## 1372                        HEYMANN,ELISA R             Senior Lecturer
    ## 1373                           HICKS,ANDREA         Assistant Professor
    ## 1374                          HIEBING,LAURA              Assoc Lecturer
    ## 1375                          HIGBY,GREGORY             Senior Lecturer
    ## 1376                       HILDNER,DAVID J.                   Professor
    ## 1377                             HILL,BETSI           Faculty Associate
    ## 1378                            HILL,JOEL R          Clinical Asst Prof
    ## 1379                        HILL,NICHOLAS J           Faculty Associate
    ## 1380                          HILL,PFANIQUE                    Lecturer
    ## 1381                       HILLMAN,NICHOLAS         Associate Professor
    ## 1382                  HILLS-MEYER,PATRICK R              Assoc Lecturer
    ## 1383                  HILTNER,AARON MICHAEL          Asst Faculty Assoc
    ## 1384                        HILYARD,STEPHEN                   Professor
    ## 1385                       HINKEL,NICHOLE L         Clinical Instructor
    ## 1386              HINRICHS,NILE CHRISTOPHER             Senior Lecturer
    ## 1387                        HIRSCH,FRANCINE                   Professor
    ## 1388                         HITCHCOCK,JOHN                   Professor
    ## 1389                    HITCHMAN,MATTHEW H.                   Professor
    ## 1390                     HITCHON,WILLIAM N.                   Professor
    ## 1391                           HITE,JESSICA         Assistant Professor
    ## 1392                   HITTINGER,CHRIS TODD         Associate Professor
    ## 1393                   HO,BENJAMIN MING-TAO          Clinical Asst Prof
    ## 1394                            HO,LI-CHING         Associate Professor
    ## 1395                                HO,LISA         Assoc Faculty Assoc
    ## 1396                             HOAG,KEVIN         Assoc Faculty Assoc
    ## 1397                          HOBAN,PAUL R.         Assistant Professor
    ## 1398                           HOCH,JOHN R.                   Professor
    ## 1399                         HOEFFERLE,MARY         Assoc Faculty Assoc
    ## 1400                        HOFACKER,EMILIE        Dir, Unspecified (8)
    ## 1401                     HOFF,LAURA HEATHER        Asst Professor (Chs)
    ## 1402                          HOFFELD,ERIKA         Clinical Instructor
    ## 1403                    HOFFMAN,ERIC JOSEPH         Assoc Faculty Assoc
    ## 1404             HOFFMEISTER,MICHAEL ROBERT          Asst Faculty Assoc
    ## 1405                       HOFSTETTER,HEIKE           Faculty Associate
    ## 1406                     HOFTYZER,MELANIE K             Senior Lecturer
    ## 1407                        HOLDEN,HAZEL M.                   Professor
    ## 1408                          HOLLAND,DUANE         Assistant Professor
    ## 1409                         HOLLAND,LESLIE         Assistant Professor
    ## 1410                        HOLLOWAY,TRACEY                   Professor
    ## 1411                           HOLMAN,SARAH         Clinical Instructor
    ## 1412                     HOLSCHBACH,CHELSEA         Clinical Instructor
    ## 1413             HOLSCHUH-HOUDEN,DEB HOUDEN          Adjunct Instructor
    ## 1414                HOLT III,JOSEPH PAYNTER         Clinical Assoc Prof
    ## 1415                          HONG,SEUNGPYO                   Professor
    ## 1416                        HONORE,FLORENCE         Assistant Professor
    ## 1417                              HOOD,SEAN              Assoc Lecturer
    ## 1418                          HOOKER,PAUL D             Senior Lecturer
    ## 1419                         HOON,MRINALINI         Assistant Professor
    ## 1420                  HOOPER-LANE,ELIZABETH             Senior Lecturer
    ## 1421                   HORA,MATTHEW TADASHI         Assistant Professor
    ## 1422                        HORNBERGER,TROY                   Professor
    ## 1423                    HORNER,VANESSA LYNN        Asst Professor (Chs)
    ## 1424                        HOROWITZ,LEAH S         Assistant Professor
    ## 1425                          HOSKINS,AARON         Associate Professor
    ## 1426                         HOTCHKISS,SARA                   Professor
    ## 1427                           HOUCK,JUDITH                   Professor
    ## 1428                    HOUDE,JEAN-FRANCOIS         Associate Professor
    ## 1429                        HOWARD,ROBERT G                   Professor
    ## 1430                              HOWE,MIKE              Assoc Lecturer
    ## 1431                          HOWE,MORGAN E              Assoc Lecturer
    ## 1432                     HOWELL,EVELYN ANNE                   Professor
    ## 1433                              HOYT,ERIC         Associate Professor
    ## 1434                           HOYT,WILLIAM                   Professor
    ## 1435                      HRYCKOWIAN,ANDREW         Assistant Professor
    ## 1436                HSIA,FLORENCE CHARLOTTE                   Professor
    ## 1437                              HSU,DAVID             Professor (Chs)
    ## 1438                             HSU,JUSTIN         Assistant Professor
    ## 1439                          HSUNG,RICHARD                   Professor
    ## 1440                             HU,JIAMIAN         Assistant Professor
    ## 1441                             HU,QUANYIN         Assistant Professor
    ## 1442                              HU,YU HEN                   Professor
    ## 1443                           HUANG,JINGYI         Assistant Professor
    ## 1444                         HUANG,KRISTINA         Assistant Professor
    ## 1445                          HUANG,QUNYING         Associate Professor
    ## 1446                          HUANG,SHAOSAI          Visiting Asst Prof
    ## 1447                              HUANG,XIN         Associate Professor
    ## 1448                             HUANG,ZHEN         Associate Professor
    ## 1449                       HUBANKS,TANYA A.                    Lecturer
    ## 1450                      HUBBARD,BREEANA N         Assoc Faculty Assoc
    ## 1451                         HUBBARD,EDWARD         Associate Professor
    ## 1452                           HUBER,GEORGE                   Professor
    ## 1453                          HUDNALL,KATIE         Assistant Professor
    ## 1454                         HUGHES,GWYNETH                    Lecturer
    ## 1455                   HULL,CHRISTINA MARIE                   Professor
    ## 1456                      HUNEEUS,ALEXANDRA                   Professor
    ## 1457                            HUNTER,PAUL       Assoc Professor (Chs)
    ## 1458                       HUNTINGTON,JOY W              Assoc Lecturer
    ## 1459                       HUNTINGTON,RANIA                   Professor
    ## 1460                           HURLEY,JAMES                   Professor
    ## 1461                           HUSTAD,KATIE                   Professor
    ## 1462                        HUTCHINS,B. IAN         Assistant Professor
    ## 1463                      HUTCHINSON,STEVEN                   Professor
    ## 1464                            HUTSON,PAUL             Professor (Chs)
    ## 1465                      HUTTENLOCHER,ANNA                   Professor
    ## 1466                          HUTTON,JEREMY                   Professor
    ## 1467                           HUYNH,JULIET         Assistant Professor
    ## 1468                           HUYNH,TU ANH         Assistant Professor
    ## 1469                             HYDE,JANET                   Professor
    ## 1470                             HYER,BRIAN                   Professor
    ## 1471                         IBARRA,ARMANDO         Associate Professor
    ## 1472                      IBELE,ERIK WARREN          Adjunct Instructor
    ## 1473                           IBER,PATRICK         Associate Professor
    ## 1474                          IFRIM,MIHAELA         Associate Professor
    ## 1475                          IKEDA,AKIHIRO                   Professor
    ## 1476                           IKEDA,SHINYA         Assistant Professor
    ## 1477                            IMHOFF,LISA              Assoc Lecturer
    ## 1478                         INEICHEN,JACOB              Assoc Lecturer
    ## 1479                      INGHAM,BARBARA H.                   Professor
    ## 1480                            INTHALY,SAM           Faculty Associate
    ## 1481                         IPSEN,PERNILLE         Associate Professor
    ## 1482                   IRIBE RAMIREZ,YVETTE              Assoc Lecturer
    ## 1483                      ISENBUEGEL,STELLA             Senior Lecturer
    ## 1484                       ISKANDAR,BERMANS                   Professor
    ## 1485                         IVANOV,MIKHAIL                    Lecturer
    ## 1486                        IVES,ANTHONY R.                   Professor
    ## 1487                             IYER,GOPAL         Assistant Professor
    ## 1488                       JABLONSKY,CLAIRE                    Lecturer
    ## 1489                     JACH,ELIZABETH ANN                    Lecturer
    ## 1490                        JACKA,ELIZABETH                    Lecturer
    ## 1491                          JACKLITZ,JILL         Clinical Instructor
    ## 1492                  JACKSON,JERLANDO F.L.                   Professor
    ## 1493                        JACKSON,MEYER B                   Professor
    ## 1494                          JACKSON,RANDY                   Professor
    ## 1495                          JACKSON,RANDY                    Lecturer
    ## 1496             JACKSON,SHERRELLE PRINCESS          Clinical Asst Prof
    ## 1497                      JACKSON,TARAKEE M         Assoc Faculty Assoc
    ## 1498                  JACOBS,CASANDRA MARIE         Clinical Instructor
    ## 1499                             JACOBS,LEA                   Professor
    ## 1500                         JACOBS,LINDSAY         Assistant Professor
    ## 1501                           JAHNS,THOMAS                   Professor
    ## 1502                       JARJOUR,NIZAR N.                   Professor
    ## 1503                       JARRARD,DAVID F.                   Professor
    ## 1504                         JASPER,CYNTHIA                   Professor
    ## 1505                             JEDD,SARAH           Faculty Associate
    ## 1506                      JEFCOATE,COLIN R.              Professor Emer
    ## 1507                        JEFFERSON,DIANE                    Lecturer
    ## 1508                           JENKINS,GINA                    Lecturer
    ## 1509                  JENNINGS,KARLENE NOEL          Instructional Spec
    ## 1510                       JENSEN,KATHERINE         Assistant Professor
    ## 1511                            JENSEN,OLAF         Associate Professor
    ## 1512                         JEONG,SEUNGGON         Assoc Faculty Assoc
    ## 1513                           JERAJ,ROBERT                   Professor
    ## 1514                             JEW,VICTOR             Senior Lecturer
    ## 1515                             JHA,SOMESH                   Professor
    ## 1516                          JIANG,HONGRUI                   Professor
    ## 1517                             JIANG,JACK                   Professor
    ## 1518                         JIANG,JIAOYANG         Associate Professor
    ## 1519                            JIANG,JIEPU         Assistant Professor
    ## 1520                  JIMENEZ,ROMMEL JAVIER       Student Services Cord
    ## 1521                               JIN,SONG                   Professor
    ## 1522                              JOG,VARUN         Assistant Professor
    ## 1523                           JOHANNES,JIM                   Professor
    ## 1524               JOHANNSEN,ERIC CHRISTIAN         Associate Professor
    ## 1525                     JOHNS,CHRISTY LYNN          Adjunct Instructor
    ## 1526                          JOHNSON,AMAUD                   Professor
    ## 1527                JOHNSON,ARLYNE HEDEMARK           Adjunct Professor
    ## 1528                          JOHNSON,BECKY          Clinical Professor
    ## 1529                    JOHNSON,CHRISTOPHER        Asst Prof Of Mil Sci
    ## 1530                        JOHNSON,DAVID W             Senior Lecturer
    ## 1531                          JOHNSON,DEREK                   Professor
    ## 1532                           JOHNSON,ERIC                   Professor
    ## 1533                        JOHNSON,JEFFREY                   Professor
    ## 1534                         JOHNSON,JENELL         Associate Professor
    ## 1535                        JOHNSON,JESSICA                   Professor
    ## 1536                  JOHNSON,KEVIN MICHAEL         Assistant Professor
    ## 1537                      JOHNSON,LEE HELEN         Assistant Professor
    ## 1538                    JOHNSON,LISA MARVEL         Assoc Faculty Assoc
    ## 1539                           JOHNSON,MARK                    Lecturer
    ## 1540                        JOHNSON,MICHAEL                    Lecturer
    ## 1541                       JOHNSON,MICHELLE           Faculty Associate
    ## 1542                JOHNSON,NATHAN BARRETTE         Assoc Faculty Assoc
    ## 1543                   JOHNSON,PAUL HERBERT                    Lecturer
    ## 1544                        JOHNSON,SHERI P       Assoc Professor (Chs)
    ## 1545                      JOHNSON,STEPHEN M         Associate Professor
    ## 1546                       JOHNSON,STERLING                   Professor
    ## 1547                      JOHNSON,SUSAN LEE                   Professor
    ## 1548                           JOHNSON,TANA         Associate Professor
    ## 1549                         JOHNSTON,SARAH         Assistant Professor
    ## 1550                         JONES,ANNIE M.                   Professor
    ## 1551                            JONES,DANNY                    Lecturer
    ## 1552                       JONES,HALLEY ANN              Assoc Lecturer
    ## 1553                            JONES,JAMAL         Assistant Professor
    ## 1554                   JONES,JANA ELIZABETH         Associate Professor
    ## 1555                         JONES,KELLI J.         Clinical Assoc Prof
    ## 1556                             JONES,MATT         Associate Professor
    ## 1557                           JONES,THOMAS                   Professor
    ## 1558                           JONES,TOMIKO         Assistant Professor
    ## 1559                           JORDAN,JERRY       Sr Student Serv Coord
    ## 1560                   JORDON-THADEN,INGRID         Assoc Faculty Assoc
    ## 1561                      JORENBY,DOUGLAS E             Professor (Chs)
    ## 1562                         JORGENSEN,JOAN         Associate Professor
    ## 1563                          JOUINI,NAJOUA                    Lecturer
    ## 1564                    JOVIC-HUMPHREY,ANJA                    Lecturer
    ## 1565                        JOYNT,ROBERT J.                   Professor
    ## 1566                          JOZWIK,SARA L         Clinical Assoc Prof
    ## 1567                              JUAREZ,AJ              Assoc Lecturer
    ## 1568                             JUDGE,MIKE           Faculty Associate
    ## 1569                          JULL,LAURA G.         Associate Professor
    ## 1570                           JUN,MYUNGHEE           Faculty Associate
    ## 1571                           JUNG,HEE SOO       Assoc Professor (Chs)
    ## 1572                         JUSZCZYK,LAURA                    Lecturer
    ## 1573                          KABBAGE,MEHDI         Associate Professor
    ## 1574                           KADAKIA,MAYA              Assoc Lecturer
    ## 1575                         KAEPPLER,HEIDI         Associate Professor
    ## 1576                         KAEPPLER,SHAWN                   Professor
    ## 1577                          KAIKSOW,FARAH        Asst Professor (Chs)
    ## 1578                          KAISER,ROBERT                   Professor
    ## 1579                          KAJI,EUGENE H       Assoc Professor (Chs)
    ## 1580                          KALAN,LINDSAY         Assistant Professor
    ## 1581                         KALEJTA,ROBERT                   Professor
    ## 1582                            KALETKA,SUE          Sr Admin Prgm Spec
    ## 1583                    KALIN,MARC LAWRENCE          Clinical Asst Prof
    ## 1584                           KALIN,NED H.                   Professor
    ## 1585                      KALLENBERGER,MIKE              Assoc Lecturer
    ## 1586                     KALLENBORN,CAROLYN                   Professor
    ## 1587                            KALRA,PRIYA                    Lecturer
    ## 1588                      KALSCHEUR,KATHRYN                    Lecturer
    ## 1589                              KAMAL,RAJ                    Lecturer
    ## 1590                               KAMP,TIM                   Professor
    ## 1591                       KANAREK,MARTY S.                   Professor
    ## 1592                         KANE,COLLEEN A           Faculty Associate
    ## 1593                         KANG,HYUNSEUNG         Assistant Professor
    ## 1594                             KANG,JUNSU         Assistant Professor
    ## 1595                         KANN,STEPHANIE       Sr Student Serv Coord
    ## 1596                     KANTROWITZ,STEPHEN                   Professor
    ## 1597                       KAPLAN,ALLISON G       Dis Faculty Associate
    ## 1598                           KAPLAN,DAVID                   Professor
    ## 1599                            KAPP,DANIEL          Adjunct Assoc Prof
    ## 1600                          KAPUST,DANIEL                   Professor
    ## 1601                         KARAJIC,ALMIRA                    Lecturer
    ## 1602                        KARASOV,WILLIAM                   Professor
    ## 1603                         KARLE,ALBRECHT                   Professor
    ## 1604                             KARP,PARRY                   Professor
    ## 1605                        KARPUKHIN,S. A.                    Lecturer
    ## 1606               KARTHIKEYAN,KRISHNAPURAM                   Professor
    ## 1607                             KASAB,JOHN                    Lecturer
    ## 1608                         KASDORF,THOMAS              Assoc Lecturer
    ## 1609                      KASIETA,ROBERT J.          Adjunct Instructor
    ## 1610                         KASPAR,CHARLES                   Professor
    ## 1611                KASTBERG,ERIN ELIZABETH          Adjunct Instructor
    ## 1612                     KASTNER,KATHLEEN A        Asst Professor (Chs)
    ## 1613                           KATANICK,RON              Assoc Lecturer
    ## 1614                           KATS,MIKHAIL         Associate Professor
    ## 1615                 KAUSHANSKAYA,MARGARITA                   Professor
    ## 1616                    KAUTZER,MEGHAN ROSE                    Lecturer
    ## 1617                      KAWAOKA,YOSHIHIRO                   Professor
    ## 1618                       KAWASAKI,JASON K         Assistant Professor
    ## 1619                         KEAN,RONALD P.           Faculty Associate
    ## 1620                             KEANE,MARK               Professor L/I
    ## 1621                        KEANE,MARTIN T.              Assoc Lecturer
    ## 1622                KECHELE,LEAH MCLAUGHLIN          Clinical Asst Prof
    ## 1623                           KECK,JAMES L                   Professor
    ## 1624                 KEDZIORA,JEREMY THOMAS              Assoc Lecturer
    ## 1625                      KEEFOVER-RING,KEN         Assistant Professor
    ## 1626                           KEELER,KASEY         Assistant Professor
    ## 1627                        KEENAN,THOMAS D        Asst Professor (Chs)
    ## 1628                         KEEPMAN,SAMUEL         Clinical Instructor
    ## 1629                    KEHE,JESSI CISEWSKI         Assistant Professor
    ## 1630                           KELES,SUNDUZ                   Professor
    ## 1631                       KELLEHER,J. PAUL         Associate Professor
    ## 1632                        KELLER,MORGAN J                    Lecturer
    ## 1633                           KELLER,NANCY                   Professor
    ## 1634                       KELLER,RICHARD C                   Professor
    ## 1635                         KELLEY,CAROLYN                   Professor
    ## 1636                    KELLEY,OLIVIA MARIE          Adjunct Instructor
    ## 1637                       KELLEY,THERESA M                   Professor
    ## 1638                         KELLIHAN,HEIDI         Clinical Assoc Prof
    ## 1639                KELLOGG,KATHRYN REBECCA         Clinical Assoc Prof
    ## 1640                            KELLY,BARON                   Professor
    ## 1641                             KELLY,CLAY                   Professor
    ## 1642                     KELLY,ELIZABETH S.           Faculty Associate
    ## 1643                            KELLY,KEVIN            Associate Dean/M
    ## 1644                           KELLY,KRISTY         Clinical Assoc Prof
    ## 1645                         KELLY,SHAWN T.       Dis Faculty Associate
    ## 1646                     KEMENY,MICHAEL L J         Assistant Professor
    ## 1647                       KENDALL,NANCY O.                   Professor
    ## 1648               KENDZIORSKI,CHRISTINA M.                   Professor
    ## 1649                            KENNAN,JOHN                   Professor
    ## 1650                          KENNEDY,DEVIN         Assistant Professor
    ## 1651                 KENNEY,CATHERINE CLARA           Faculty Associate
    ## 1652                         KENNEY,SHANNON                   Professor
    ## 1653                   KENNY,AMANDA DILLARD             Senior Lecturer
    ## 1654                  KENOYER,JONATHAN MARK                   Professor
    ## 1655                       KENT,AUTUMN EXUM                   Professor
    ## 1656                              KENT,PAUL          Adjunct Instructor
    ## 1657                        KERCHEVAL,JESSE                   Professor
    ## 1658                           KERN,ADAM L.                   Professor
    ## 1659                         KERR, MARGARET         Assistant Professor
    ## 1660                KEULER,NICHOLAS STEPHEN         Assoc Faculty Assoc
    ## 1661                         KEYSER,RICHARD             Senior Lecturer
    ## 1662                         KHAN,ASAD RAZA              Assoc Lecturer
    ## 1663                           KHANNA,VARUN                    Lecturer
    ## 1664                        KHASAWNEH,SAMER           Faculty Associate
    ## 1665                           KHATIB,HASAN                   Professor
    ## 1666                           KHEDUP,JAMPA             Senior Lecturer
    ## 1667                   KIDWELL,AMANDA LYNNE                    Lecturer
    ## 1668                           KIEFER,DAVID          Clinical Asst Prof
    ## 1669                            KIESER,MARA             Professor (Chs)
    ## 1670                          KIGEYA,DANIEL                    Lecturer
    ## 1671                  KIHSLINGER,JANE ELLEN         Assistant Professor
    ## 1672                            KILEN,SARAH          Clinical Asst Prof
    ## 1673                      KILEY,PATRICIA J.                   Professor
    ## 1674                         KILGUS,STEPHEN         Associate Professor
    ## 1675                            KIM,CHANWOO         Associate Professor
    ## 1676                            KIM,CHARLES         Associate Professor
    ## 1677                            KIM,HIEYOON         Assistant Professor
    ## 1678                           KIM,JEE-SEON                   Professor
    ## 1679                          KIM,KYUNG-SUN                   Professor
    ## 1680                          KIM,KYUNGMANN                   Professor
    ## 1681                             KIM,MONICA         Assistant Professor
    ## 1682                              KIM,NAM C         Associate Professor
    ## 1683                           KIM,SUNG SIN                   Professor
    ## 1684                           KIM,YEA-SEUL         Assistant Professor
    ## 1685                                 KIM,YJ         Assistant Professor
    ## 1686                          KIM,YOUNG MIE                   Professor
    ## 1687                          KIM,YOUNGHYUN         Assistant Professor
    ## 1688                          KIMBLE,JUDITH                   Professor
    ## 1689                            KIMMEL,PAUL             Senior Lecturer
    ## 1690                        KIMPLE,MICHELLE         Associate Professor
    ## 1691                           KIMPLE,RANDY         Associate Professor
    ## 1692                   KIND,AMY JO HAAVISTO         Associate Professor
    ## 1693                           KING,BARBARA         Associate Professor
    ## 1694                          KING,M. BRUCE           Faculty Associate
    ## 1695                             KING,STEVE          Adjunct Instructor
    ## 1696                         KINNEY,MELISSA         Assistant Professor
    ## 1697                     KINTNER,EILEEN KAE                   Professor
    ## 1698                           KINZLEY,JUDD         Associate Professor
    ## 1699                           KIRCH,JEREMY          Asst Faculty Assoc
    ## 1700           KIRCHDOERFER,ROBERT NICHOLAS         Assistant Professor
    ## 1701                      KIRCHGASLER,CHRIS         Assistant Professor
    ## 1702                      KIRCHGASLER,KATIE         Assistant Professor
    ## 1703                   KIRK,GWENDOLYN SARAH                    Lecturer
    ## 1704                      KIRKORIAN,HEATHER         Associate Professor
    ## 1705                KIRKPATRICK,BRIAN WAYNE                   Professor
    ## 1706                      KIRPALANI,RISHABH         Assistant Professor
    ## 1707                            KITA,ANGELA         Assoc Faculty Assoc
    ## 1708                             KLATT,JOHN          Assistant Dean/M-L
    ## 1709                        KLEEDEHN,MARK G        Asst Professor (Chs)
    ## 1710                    KLEHR,MARY RAIMONDA                    Lecturer
    ## 1711                         KLEIJWEGT,MARC                   Professor
    ## 1712                     KLEIN,BRUCE STEVEN                   Professor
    ## 1713                         KLIEWER,MARK A                   Professor
    ## 1714                        KLINGBEIL,DAVID         Assistant Professor
    ## 1715                       KLINGELE,CECELIA         Associate Professor
    ## 1716                        KLINGENBERG,DAN                   Professor
    ## 1717                           KLOCKE,SONJA         Associate Professor
    ## 1718                             KLUG,HEINZ                   Professor
    ## 1719                         KNEZEVIC,IRENA                   Professor
    ## 1720                          KNISHKA,SCOTT          Clinical Asst Prof
    ## 1721                   KNOCH,DANIEL WILLIAM             Professor (Chs)
    ## 1722                            KNOLL,LAURA                   Professor
    ## 1723                     KNOX,KJERSTI ELISE  Clinical Adjunct Asst Prof
    ## 1724                        KNUTSON,JASON J          Adjunct Instructor
    ## 1725                         KOBERNUSZ,JEFF         Clinical Instructor
    ## 1726                              KOCH,PAUL         Associate Professor
    ## 1727                            KODESH,NEIL                   Professor
    ## 1728                            KOENIG,JANE             Senior Lecturer
    ## 1729                           KOENIGS,MIKE                   Professor
    ## 1730                            KOH,LINDSAY           Faculty Associate
    ## 1731                           KOKJOHN,SAGE         Associate Professor
    ## 1732                             KOKO,MARIE              Assoc Lecturer
    ## 1733                       KOLKOWITZ,SHIMON         Assistant Professor
    ## 1734                       KOLOWRAT,KATIE M         Clinical Instructor
    ## 1735                      KOLTYN,KELLI FAYE                   Professor
    ## 1736                          KONG,JOOYOUNG         Assistant Professor
    ## 1737                           KONOPKA,ADAM         Assistant Professor
    ## 1738                            KONZ,ANDREA              Assoc Lecturer
    ## 1739                          KOPACEK,KAREN       Assoc Professor (Chs)
    ## 1740                 KORLAKAI VINAYAK,RAMYA         Assistant Professor
    ## 1741                          KORNBLUM,RENA             Senior Lecturer
    ## 1742                  KOROSEC,FRANK RICHARD             Professor (Chs)
    ## 1743                        KOSS,PHILLIP A.          Adjunct Instructor
    ## 1744                    KOTELNICKI,MARYRUTH       Assoc Student Sv Spec
    ## 1745                 KOTLOSKI,ROBERT JOSEPH         Assistant Professor
    ## 1746                         KOTULLA,RALF C              Assoc Lecturer
    ## 1747                              KOU,SINDO                   Professor
    ## 1748                          KOUTRIS,PARIS         Assistant Professor
    ## 1749                       KOWALKOWSKI,ANNA              Assoc Lecturer
    ## 1750                      KOWALSKI,ALYCIA A         Clinical Instructor
    ## 1751                             KOZA,JULIA                   Professor
    ## 1752                KRABBENHOFT,KAREN MARIE             Senior Lecturer
    ## 1753                         KRACHEY,JOSEPH           Faculty Associate
    ## 1754                       KRAHN,ELLEN JEAN         Clinical Instructor
    ## 1755                   KRANNER,PAUL WILLIAM       Assoc Professor (Chs)
    ## 1756          KRATTIGER-ZILTENER,NANCY JOAN         Assoc Faculty Assoc
    ## 1757                         KRAUSKOPF,SARA       Assoc Instructnl Spec
    ## 1758            KRAUTHAMER-MALONEY,AMY BETH              Assoc Lecturer
    ## 1759                            KREEGER,PAM         Associate Professor
    ## 1760                       KREITMAIR,KAROLA         Assistant Professor
    ## 1761                   KRISHNASWAMY,BHUVANA         Assistant Professor
    ## 1762                        KROLL,AMY KNOTT         Clinical Assoc Prof
    ## 1763                          KROUK,DEAN N.         Associate Professor
    ## 1764                          KRUEGER,KATIE                    Lecturer
    ## 1765                           KRUG,HEATHER         Clinical Assoc Prof
    ## 1766                            KRUGER,ERIC                   Professor
    ## 1767                    KRUMMEN-LEE,GAIL A.         Clinical Instructor
    ## 1768                          KRUPENKIN,TOM         Associate Professor
    ## 1769                       KRYSAN,PATRICK J                   Professor
    ## 1770                       KUBSCH,SYLVIA M.           Faculty Associate
    ## 1771                   KUCHARIK,CHRISTOPHER                   Professor
    ## 1772                             KUCHER,JAN           Adjunct Professor
    ## 1773                           KUCHNIA,ADAM         Assistant Professor
    ## 1774                           KUCIN,AMY V.                    Lecturer
    ## 1775                       KUEMMEL,ANDREW L         Assoc Faculty Assoc
    ## 1776                            KUHL,ASHLEY       Sr Clin Genetic Couns
    ## 1777                     KUHN,BRIANNA RENEE                    Lecturer
    ## 1778                         KUHRASCH,CINDY           Faculty Associate
    ## 1779                            KUKA,RONALD           Faculty Associate
    ## 1780                           KULIG,STEVEN              Assoc Lecturer
    ## 1781                          KUMAR,SATHISH         Associate Professor
    ## 1782                           KUO,WAN-CHIN                    Lecturer
    ## 1783                            KURTZ,ROBIN       Dis Faculty Associate
    ## 1784                           KURUTZ,MARIA          Asst Faculty Assoc
    ## 1785                         KUZUHARA,LOREN             Senior Lecturer
    ## 1786                             KWAN,JASON         Associate Professor
    ## 1787                        KWASNY,MICHELLE           Faculty Associate
    ## 1788                    KWEKKEBOOM,KRISTINE                   Professor
    ## 1789                KWIECINSKI,BROOKE RENEE         Clinical Assoc Prof
    ## 1790                            KWON,DOHYUN          Visiting Asst Prof
    ## 1791                              KWON,GLEN                   Professor
    ## 1792                           KWON,OH HOON         Assoc Faculty Assoc
    ## 1793                            KYDD,ANDREW                   Professor
    ## 1794                       LA ROWE,TARA LEA         Assoc Faculty Assoc
    ## 1795                                 LA,CHI           Adjunct Asst Prof
    ## 1796                        LABELLE,SUSAN M           Adjunct Professor
    ## 1797                         LABOSKI,CARRIE                   Professor
    ## 1798                          LACROSSE,TONY       Instructor Of Mil Sci
    ## 1799                           LAESEKE,PAUL         Assistant Professor
    ## 1800                         LAGALLY,MAX G.              Professor Emer
    ## 1801                          LAGMAN,EILEEN         Assistant Professor
    ## 1802                            LAGRO,JAMES                   Professor
    ## 1803                          LAHTI,JOHN L.           Adjunct Asst Prof
    ## 1804                         LAI,HUICHUAN J                   Professor
    ## 1805                           LAJCAK,RENEE             Senior Lecturer
    ## 1806                          LAKES,RODERIC                   Professor
    ## 1807                           LAMBERT,PAUL                   Professor
    ## 1808                       LAMMING,DUDLEY W         Associate Professor
    ## 1809                           LAMONT,LIANA           Faculty Associate
    ## 1810                     LANDESS,JACQUELINE  Clinical Adjunct Asst Prof
    ## 1811                  LANDGRAF,THOMAS ALLAN             Senior Lecturer
    ## 1812                         LANDICK,ROBERT                   Professor
    ## 1813                        LANDIS,CLARK R.                   Professor
    ## 1814                    LANG,JOSHUA MICHAEL         Associate Professor
    ## 1815                    LANG,LAURA MICHELLE         Assoc Faculty Assoc
    ## 1816                      LANGVA,GLORIANN F                    Lecturer
    ## 1817                    LANIUS,JESSICA BESS                    Lecturer
    ## 1818                         LANKAU,RICHARD         Associate Professor
    ## 1819                      LAPIN,JOSHUA ADAM         Assoc Faculty Assoc
    ## 1820                       LAPINA,ELIZABETH         Associate Professor
    ## 1821                        LAPLANTE,MARK J             Senior Lecturer
    ## 1822                        LAPLANTE,STACIE         Associate Professor
    ## 1823                          LAPOINT,PAIGE                    Lecturer
    ## 1824                         LAPORTA,JIMENA         Assistant Professor
    ## 1825                     LARGET,BRET ROBERT                   Professor
    ## 1826                       LARK,TYLER JAMES                    Lecturer
    ## 1827                          LAROCHE,CHRIS             Senior Lecturer
    ## 1828                   LARSEN-KLODD,KATHRYN         Assoc Faculty Assoc
    ## 1829                       LARSON,ELIZABETH         Associate Professor
    ## 1830                  LARSON,JENNIFER CISKE        Asst Professor (Chs)
    ## 1831                       LARSON,LAURIE J.            Senior Scientist
    ## 1832        LARSON-GUENETTE,JULIE CHRISTINE         Assoc Faculty Assoc
    ## 1833                         LASKEY,FRANCES                    Lecturer
    ## 1834                        LATIMER,TIMOTHY           Faculty Associate
    ## 1835                    LATTIS,JAMES MARION           Faculty Associate
    ## 1836                          LAUGHON,ALLEN              Professor Emer
    ## 1837                         LAUHON,CHARLES         Associate Professor
    ## 1838                         LAURENZ,JEAN M         Assistant Professor
    ## 1839                      LAUVER,DIANE RUTH                   Professor
    ## 1840                        LAVIN,KELLY ANN          Clinical Asst Prof
    ## 1841                    LAWLER,JAMES EDWARD                   Professor
    ## 1842                         LAYOUN,MARY N.                   Professor
    ## 1843                          LAZARIAN,ALEX                   Professor
    ## 1844                               LE,HAU D         Assistant Professor
    ## 1845                       LECLAIR, JESSICA         Clinical Instructor
    ## 1846                      LECUYER,TRISTAN S                   Professor
    ## 1847                    LEDERER,SUSAN MARIE                   Professor
    ## 1848                           LEDESMA,EDNA         Assistant Professor
    ## 1849                             LEE,ALICIA         Assistant Professor
    ## 1850                        LEE,CAROL EUNMI                   Professor
    ## 1851                              LEE,CHOUA                    Lecturer
    ## 1852                              LEE,GRACE         Assoc Faculty Assoc
    ## 1853                              LEE,HARRY          Visiting Asst Prof
    ## 1854                              LEE,HELEN         Associate Professor
    ## 1855                               LEE,JOHN                   Professor
    ## 1856                            LEE,JONAS J       Assoc Professor (Chs)
    ## 1857                           LEE,KANGWOOK         Assistant Professor
    ## 1858                              LEE,LAURA         Clinical Instructor
    ## 1859                             LEE,RACHEL          Clinical Asst Prof
    ## 1860                             LEE,STACEY                   Professor
    ## 1861                                LEE,TEV                    Lecturer
    ## 1862                          LEE,YOUNGSOOK         Associate Professor
    ## 1863                    LEES,THOMAS MICHAEL                    Lecturer
    ## 1864                         LEFF,PAUL ADAM                    Lecturer
    ## 1865                         LEGAULT,HOBBES         Assoc Faculty Assoc
    ## 1866                         LEGENZA,LAUREL         Assoc Faculty Assoc
    ## 1867                               LEI,REED         Assistant Professor
    ## 1868                     LEITH,ELIZABETH A.                    Lecturer
    ## 1869                           LEKO,MELINDA                   Professor
    ## 1870                   LEMASTER,TRACY WENDT                    Lecturer
    ## 1871                 LEMIRAND-POEPPING,DAWN           Faculty Associate
    ## 1872                          LEMPP,STEFFEN                   Professor
    ## 1873                           LENNIX,SHAWN         Clinical Instructor
    ## 1874                           LENTZ,RASMUS                   Professor
    ## 1875                      LEONARD,KATHERINE         Clinical Instructor
    ## 1876                          LEONE,VANESSA         Assistant Professor
    ## 1877                         LEPOWSKY,MARIA                   Professor
    ## 1878                            LERMAN,OMER         Clinical Instructor
    ## 1879                       LESIEUTRE,BERNIE                   Professor
    ## 1880                        LESLIE,TREVOR M          Visiting Asst Prof
    ## 1881                        LESSARD,LAURENT         Assistant Professor
    ## 1882                         LEVCHENKO,ALEX                   Professor
    ## 1883                       LEVCHENKO,POLINA          Asst Faculty Assoc
    ## 1884                  LEVENSON,BARRY MARTIN          Adjunct Instructor
    ## 1885                          LEVERTY,TYLER         Associate Professor
    ## 1886                         LEVIN,KEITH D.         Assistant Professor
    ## 1887                          LEVINE,OLIVER         Associate Professor
    ## 1888                     LEWIS,ALICE KELSEY              Assoc Lecturer
    ## 1889                   LEWIS,DAVID LAWRENCE           Adjunct Professor
    ## 1890                          LEWIS,PETER W         Associate Professor
    ## 1891                       LEWIS,SHANA RUTH          Adjunct Instructor
    ## 1892                   LEWIS-WILLIAMS,TRACY           Faculty Associate
    ## 1893                          LI,CHIAO-PING                   Professor
    ## 1894                               LI,JAMES         Assistant Professor
    ## 1895                            LI,JINGSHAN                   Professor
    ## 1896                                  LI,KE         Assistant Professor
    ## 1897                             LI,LINGJUN                   Professor
    ## 1898                                 LI,MIN             Senior Lecturer
    ## 1899                                 LI,NAN         Assistant Professor
    ## 1900                                 LI,QIN         Associate Professor
    ## 1901                              LI,SHARON         Assistant Professor
    ## 1902                              LI,WAN-JU         Associate Professor
    ## 1903                              LI,WEIJIA         Assistant Professor
    ## 1904                               LI,YAFEI                   Professor
    ## 1905                                 LI,YIN         Assistant Professor
    ## 1906                              LI,YUHANG         Associate Professor
    ## 1907                           LIANG,YINGYU         Assistant Professor
    ## 1908                              LIANG,YUN         Assistant Professor
    ## 1909                             LIDOR,ANNE             Professor (Chs)
    ## 1910                            LIEBE,ETHAN              Assoc Lecturer
    ## 1911                   LIGHT,MICHAEL THOMAS         Associate Professor
    ## 1912                          LIKOS,WILLIAM                   Professor
    ## 1913                          LIM,BYUNG-JIN         Associate Professor
    ## 1914                           LIM,CHAEYOON                   Professor
    ## 1915                              LIM,CI JI         Assistant Professor
    ## 1916                            LIM,SIN YIN        Asst Professor (Chs)
    ## 1917                   LIN,JASON CHIEH-SHEN             Senior Lecturer
    ## 1918                          LINDBERG,SARA        Asst Professor (Chs)
    ## 1919                         LINDEMANN,ABBY                    Lecturer
    ## 1920                      LINDEROTH,JEFFREY                   Professor
    ## 1921                            LINDLEY,BEN         Assistant Professor
    ## 1922                          LINDROTH,RICK                   Professor
    ## 1923                         LINDSAY,KEISHA         Associate Professor
    ## 1924                        LINDSEY,MELISSA           Faculty Associate
    ## 1925                LINDSTROM,TIMOTHY DAVID              Assoc Lecturer
    ## 1926                    LINSMEIER,THOMAS J.                   Professor
    ## 1927                            LINTNER,KIM         Clinical Instructor
    ## 1928                LINZMEIER,BENJAMIN JOHN              Assoc Lecturer
    ## 1929                          LIPASTI,MIKKO                   Professor
    ## 1930                    LIPINSKI,ROBERT JAN         Associate Professor
    ## 1931                           LISOWSKI,DAN         Associate Professor
    ## 1932                        LITOVSKY,RUTH Y                   Professor
    ## 1933                      LITZELMAN,KRISTIN         Assistant Professor
    ## 1934                                 LIU,BO                   Professor
    ## 1935                              LIU,GLENN                   Professor
    ## 1936                              LIU,KAIBO         Associate Professor
    ## 1937                               LIU,QING         Associate Professor
    ## 1938                                LIU,RAN         Assistant Professor
    ## 1939                    LIVANOS,CHRISTOPHER                   Professor
    ## 1940                        LIVORNI,ERNESTO                   Professor
    ## 1941                       LIWE,AMELIA JOAN           Faculty Associate
    ## 1942                            LLOYD,SARAH         Associate Scientist
    ## 1943                     LO SARDO,VALENTINA         Assistant Professor
    ## 1944                           LO,ADELINE Y         Assistant Professor
    ## 1945                         LOCONTE,NOELLE         Associate Professor
    ## 1946                               LOEB,DAN                   Professor
    ## 1947                        LOEBER,SAMANTHA          Clinical Asst Prof
    ## 1948                           LOEWEN,CARIN          Asst Faculty Assoc
    ## 1949                       LOFTON,LAUREN K.                    Lecturer
    ## 1950                            LOH,PO-LING         Associate Professor
    ## 1951                            LOH,WEI-YIN                   Professor
    ## 1952                 LOHEIDE II,STEVEN PAUL                   Professor
    ## 1953                        LOKUTA,ANDREW J           Faculty Associate
    ## 1954        LONDON-JOHNSON,ANTOINETTE MARIE              Assoc Lecturer
    ## 1955                      LONG,MICAH THOMAS        Asst Professor (Chs)
    ## 1956                              LONG,PETE         Assoc Faculty Assoc
    ## 1957                          LONG,XIAOYANG         Assistant Professor
    ## 1958                      LONGO,LANCE PETER Clinical Adjunct Assoc Prof
    ## 1959                             LOOK,KEVIN         Assistant Professor
    ## 1960                            LOPEZ,JASON         Assistant Professor
    ## 1961                             LOPEZ,LORI         Associate Professor
    ## 1962                LOPEZ-HERNANDEZ,ARNOLDO                    Lecturer
    ## 1963                            LOR,MAICHOU         Assistant Professor
    ## 1964                       LORD PLUMMER,KIM             Senior Lecturer
    ## 1965                       LOTHARY,BRITTA N         Clinical Instructor
    ## 1966                            LOTHE,KATIE         Clinical Assoc Prof
    ## 1967                      LOTLIKAR,SUSHMITA                    Lecturer
    ## 1968                          LOTTA,CORISSA           Faculty Associate
    ## 1969                            LOUDEN,MARK                   Professor
    ## 1970                         LOUIE,NICOLE L         Assistant Professor
    ## 1971                            LOVE,HAILEY         Assistant Professor
    ## 1972                 LOVELACE,DAVID MICHAEL         Assistant Scientist
    ## 1973                           LOWE,CHLORIS                    Lecturer
    ## 1974                           LOYD,JENNA M         Associate Professor
    ## 1975                            LU,QIONGSHI         Assistant Professor
    ## 1976                      LUBNER,SAM JOSEPH       Assoc Professor (Chs)
    ## 1977                         LUBSEN,JULIA R        Asst Professor (Chs)
    ## 1978                            LUBY,CLAIRE                    Lecturer
    ## 1979                          LUCEY,JOHN A.                   Professor
    ## 1980                        LUCEY,MICHAEL R                   Professor
    ## 1981                             LUCK,BRIAN         Assistant Professor
    ## 1982                    LUDOIS,DANIEL COLIN         Associate Professor
    ## 1983                 LUDVIK,GEOFFREY EDMOND              Assoc Lecturer
    ## 1984                       LUDWIG,KIP ALLAN         Associate Professor
    ## 1985                            LUEDTKE,JIM                   Professor
    ## 1986                        LUKSZYS,PETER B             Senior Lecturer
    ## 1987                       LUNASIN,EVELYN M         Visiting Assoc Prof
    ## 1988                        LUND,JANE RENEE          Clinical Asst Prof
    ## 1989                            LUPYAN,GARY                   Professor
    ## 1990                      LUTER,DAVID GAVIN              Assoc Lecturer
    ## 1991                      LUTZ,ROBERT SCOTT         Associate Professor
    ## 1992                   LUZZIO,CHRISTOPHER C       Assoc Professor (Chs)
    ## 1993                              LYNCH,DAN         Associate Professor
    ## 1994                          LYNN,DAVID M.                   Professor
    ## 1995                       LYONS,JOHN DAVID              Assoc Lecturer
    ## 1996                                 MA,CHU         Assistant Professor
    ## 1997                           MA,ZHENQIANG                   Professor
    ## 1998                   MACASAET,DAVID WEBER                    Lecturer
    ## 1999                        MACAULAY,MONICA                   Professor
    ## 2000                    MACDONALD,MARYELLEN                   Professor
    ## 2001                            MACE,DAKOTA                    Lecturer
    ## 2002                      MACGUIDWIN,ANN E.                   Professor
    ## 2003                          MACHADO,EMILY         Assistant Professor
    ## 2004                       MACHLEIDT,THOMAS           Adjunct Professor
    ## 2005                        MACHOIAN,RONALD             Senior Lecturer
    ## 2006                            MACKAY,JOHN         Associate Professor
    ## 2007                        MACOMBER,KELSEY              Assoc Lecturer
    ## 2008                         MADDEN,CAITLIN          Adjunct Instructor
    ## 2009                           MADDEN,HALEY         Outreach Specialist
    ## 2010                         MADUREIRA,LUIS                   Professor
    ## 2011                          MAEDA,HIROSHI         Associate Professor
    ## 2012                            MAES,MARINA        Asst Professor (Chs)
    ## 2013                         MAGANTI,RAMA K             Professor (Chs)
    ## 2014                       MAGNOLFI,LORENZO         Assistant Professor
    ## 2015                MAGNUSON,KATHERINE ANNE                   Professor
    ## 2016                        MAGUIRE,MICHAEL         Assoc Faculty Assoc
    ## 2017                        MAHER,JESSICA M                    Lecturer
    ## 2018                        MAHMOUD,AHMED I         Assistant Professor
    ## 2019                   MAIER,JOSEPH MICHAEL          Adjunct Instructor
    ## 2020                     MAJUMDER,ERICA L-W         Assistant Professor
    ## 2021                        MAJUMDER,KINJAL         Assistant Professor
    ## 2022                         MAKI,DENNIS G.              Professor Emer
    ## 2023                        MAKI,LYNN MARIE              Assoc Lecturer
    ## 2024                        MALECKI,KRISTEN         Associate Professor
    ## 2025                       MALITSKY,EUGENIA                    Lecturer
    ## 2026                         MALLOY,MATTHEW           Adjunct Asst Prof
    ## 2027               MALONE,KRISTA-LEE MEGHAN           Faculty Associate
    ## 2028                    MALONE,MARY KATHRYN           Faculty Associate
    ## 2029                MALSON-HUDDLE,ELIZABETH             Senior Lecturer
    ## 2030                            MANDEL,MARK         Associate Professor
    ## 2031                         MANI,B. VENKAT                   Professor
    ## 2032                       MANKOWSKI,JOEL E             Senior Lecturer
    ## 2033                     MANN,TERRY MICHAEL             Senior Lecturer
    ## 2034                         MANS,CHRISTOPH         Clinical Assoc Prof
    ## 2035                                 MAO,LU         Assistant Professor
    ## 2036                           MARA,KATHRYN              Assoc Lecturer
    ## 2037                    MARAVELIAS,CHRISTOS                   Professor
    ## 2038                       MARCHE,JORDAN D.             Senior Lecturer
    ## 2039                   MARCOTT,SHAUN ANDREW         Associate Professor
    ## 2040                      MARCOUILLER,DAVID                   Professor
    ## 2041                     MARES,MARIE-LOUISE                   Professor
    ## 2042               MARES-PERLMAN,JULIE ANNE                   Professor
    ## 2043                        MARGOLIS,AMANDA        Asst Professor (Chs)
    ## 2044                      MARI-BEFFA,GLORIA                   Professor
    ## 2045                    MARIN-SPIOTTA,ERIKA                   Professor
    ## 2046                 MARINEZ LORA,ANE MARIA                    Lecturer
    ## 2047                         MARKEL,MARK D.                   Professor
    ## 2048                            MARKER,PAUL                   Professor
    ## 2049                       MARLER,CATHERINE                   Professor
    ## 2050                       MAROON,ELIZABETH         Assistant Professor
    ## 2051                MARQUES,FERNANDO JAVIER         Clinical Assoc Prof
    ## 2052                       MARQUEZ,BENJAMIN                   Professor
    ## 2053                      MARSH FINCO,JAMIE         Assoc Faculty Assoc
    ## 2054                              MARSH,ANN              Assoc Lecturer
    ## 2055                         MARSHALL,NANCY                   Professor
    ## 2056                 MARSHALL,NOWELL ANDREW             Senior Lecturer
    ## 2057                 MARSHALL,SIMON LINDSAY         Associate Professor
    ## 2058                      MARTELL,JEFFREY D         Assistant Professor
    ## 2059                       MARTIN,ANN SMART                   Professor
    ## 2060                            MARTIN,BETH             Professor (Chs)
    ## 2061                          MARTIN,DARREN       Student Services Cord
    ## 2062                         MARTIN,JESSICA           Adjunct Professor
    ## 2063                            MARTIN,JOHN              Assoc Lecturer
    ## 2064                 MARTIN,JONATHAN EDWARD                   Professor
    ## 2065                           MARTIN,KERRY           Faculty Associate
    ## 2066                            MARTIN,LISA                   Professor
    ## 2067                      MARTIN,THOMAS F J                   Professor
    ## 2068                        MARTINEZ,MARCOS              Assoc Lecturer
    ## 2069                             MARTINS,JP         Assistant Professor
    ## 2070                            MARTY,SARAH           Faculty Associate
    ## 2071                  MARULASIDDAPPA,SURESH                   Professor
    ## 2072                         MASON,ANDREA H                   Professor
    ## 2073                           MASON,JOSEPH                   Professor
    ## 2074                          MASROUR,FARID         Associate Professor
    ## 2075                    MASSOGLIA,MICHAEL A                   Professor
    ## 2076                         MASSON,PATRICK                   Professor
    ## 2077                        MASTERS,KRISTYN                   Professor
    ## 2078                            MATHEWS,JIM                    Lecturer
    ## 2079                      MATHIEU,ROBERT D.                   Professor
    ## 2080                     MATSUMURA,ELLA MAE                   Professor
    ## 2081                    MATTHEWS,PERCIVAL G         Associate Professor
    ## 2082                         MATTHIES,ROBIN              Assoc Lecturer
    ## 2083                           MATTILA,DANE                    Lecturer
    ## 2084                        MATTIS,KRISTINE          Asst Faculty Assoc
    ## 2085                   MATULIONIS,GAUDRIMAS        Asst Prof Of Mil Sci
    ## 2086                           MAUK,MATTHEW                    Lecturer
    ## 2087                       MAVRIKAKIS,MANOS                   Professor
    ## 2088                             MAWST,LUKE                   Professor
    ## 2089                        MAXIM,LAURENTIU                   Professor
    ## 2090                          MAYER,KENNETH                   Professor
    ## 2091                        MAYERS,JOSHUA B           Adjunct Asst Prof
    ## 2092                         MAYHEW,BRIAN W                   Professor
    ## 2093                     MAYNARD,DOUGLAS W.                   Professor
    ## 2094             MC ANULTY,JONATHAN FRANCIS                   Professor
    ## 2095                          MC CAMMON,DAN                   Professor
    ## 2096                           MC CLAIN,ROB           Faculty Associate
    ## 2097                        MC DANIEL,SARAH                    Lecturer
    ## 2098                        MC LEOD,DOUGLAS                   Professor
    ## 2099             MC SHANE-HELLENBRAND,KAREN           Faculty Associate
    ## 2100                        MCANDREWS,CAREY         Associate Professor
    ## 2101                 MCAULIFFE,NOREEN MARIE              Assoc Lecturer
    ## 2102                        MCBRIDE,ERIN K.         Clinical Assoc Prof
    ## 2103                   MCCALLUM,JAMES SCOTT          Adjunct Assoc Prof
    ## 2104                           MCCARTHY,LIZ                  Sr Advisor
    ## 2105                         MCCARY,LINDSAY  Clinical Adjunct Asst Prof
    ## 2106                          MCCLEAN,MEGAN         Assistant Professor
    ## 2107                            MCCLURG,TIM             Senior Lecturer
    ## 2108                   MCCORD,ALEIA INGULLI         Assoc Faculty Assoc
    ## 2109                   MCCOY,ALFRED WILLIAM                   Professor
    ## 2110                                MCCOY,M           Faculty Associate
    ## 2111                             MCCOY,SARA        Asst Professor (Chs)
    ## 2112                   MCCULLEY,DAVID JAMES         Assistant Professor
    ## 2113                          MCCULLOH,KATE         Associate Professor
    ## 2114                      MCCULLOUGH,CHAD J              Assoc Lecturer
    ## 2115                       MCCURDY,MARTHA L                    Lecturer
    ## 2116                        MCDERMOTT,MEGAN                    Lecturer
    ## 2117                     MCDERMOTT,ROBERT F                   Professor
    ## 2118                MCDONALD,DAVID MACLAREN                   Professor
    ## 2119                        MCDONALD,JOSEPH              Assoc Lecturer
    ## 2120                 MCDONALD,PETER DOUGLAS         Assistant Professor
    ## 2121                       MCDONNELL,TERESA           Adjunct Professor
    ## 2122                     MCDOWELL,COLLEEN M         Assistant Professor
    ## 2123                      MCFARLAND,RICHARD         Associate Professor
    ## 2124                         MCGARR,KATHRYN         Assistant Professor
    ## 2125                       MCGLAMERY,THOMAS           Faculty Associate
    ## 2126                      MCGRANAHAN,PAMELA         Clinical Assoc Prof
    ## 2127                        MCINNES,BRIAN D         Associate Professor
    ## 2128                   MCKELVEY,CHRISTOPHER                    Lecturer
    ## 2129                          MCKEOWN,JAMES                   Professor
    ## 2130             MCKINNEY DE ROYSTON,MAXINE         Assistant Professor
    ## 2131                          MCKINNON,SARA         Associate Professor
    ## 2132                        MCKOWN,KEVIN M.          Clinical Asst Prof
    ## 2133                       MCLELLAN,GILLIAN         Associate Professor
    ## 2134                   MCLEOD,ZACHARY DAVID          Admin Program Spec
    ## 2135                      MCMAHON,KATHERINE                   Professor
    ## 2136                      MCMAHON,ROBERT J.                   Professor
    ## 2137                         MCMASTER,JAMES         Assistant Professor
    ## 2138                    MCMILLAN,ALAN BLAIR       Assoc Professor (Chs)
    ## 2139                         MCMILLAN,DAWNA          Clinical Asst Prof
    ## 2140                 MCNAMARA,NICHOLAS JOEL          Adjunct Instructor
    ## 2141                  MCNEEL,DOUGLAS GORDON                   Professor
    ## 2142               MCQUILLAN,MOLLIE THERESE         Assistant Professor
    ## 2143                           MEAD,JULIE F                   Professor
    ## 2144                     MEAD,SCOTT MICHAEL         Clinical Assoc Prof
    ## 2145                         MECOZZI,SANDRO                   Professor
    ## 2146                           MEDINA,RUBEN                   Professor
    ## 2147                           MEDNICK,ADAM                    Lecturer
    ## 2148                      MEDOW,JOSHUA ERIC         Associate Professor
    ## 2149                           MEHLE,ANDREW         Associate Professor
    ## 2150                           MEIER,ALISON              Assoc Lecturer
    ## 2151                          MEILLER,LARRY              Professor Emer
    ## 2152                   MEKEEL,WILLIAM JAMES             Senior Lecturer
    ## 2153                  MELLO,ANTONIO SAMPAIO                   Professor
    ## 2154                           MELLOR,SCOTT       Dis Faculty Associate
    ## 2155                      MENDONCA,ENEIDA A       Honorary Assoc/Fellow
    ## 2156                   MENDOZA RIVERA,HENRY             Senior Lecturer
    ## 2157                      MENECHELLA,GRAZIA         Associate Professor
    ## 2158                           MENZEL,ANNIE         Assistant Professor
    ## 2159                        MERCADO,SARLI E             Senior Lecturer
    ## 2160                       MERMELSTEIN,OMER          Visiting Asst Prof
    ## 2161                  MERRINS,MATTHEW JAMES         Assistant Professor
    ## 2162                            MERTZ,JANET                   Professor
    ## 2163                          MESSINA,JAMES         Associate Professor
    ## 2164                   METCALF,CARISSA ROSE              Assoc Lecturer
    ## 2165                            MEURIS,JIRS         Assistant Professor
    ## 2166                           MEYER,DANIEL                   Professor
    ## 2167                      MEYER,GABRIELE E.           Faculty Associate
    ## 2168                         MEYER,LAUREN N                    Lecturer
    ## 2169                    MEYER,MARK BENJAMIN              Assoc Lecturer
    ## 2170                          MEYERAND,BETH                   Professor
    ## 2171                        MEYERS,JENNIFER                    Lecturer
    ## 2172                          MEYERS,ROSS O         Assoc Faculty Assoc
    ## 2173                       MEYERS,STEPHEN R                   Professor
    ## 2174                               MEYN,ION         Assistant Professor
    ## 2175                         MIALIK,HEATHER        Instructl Prg Mgr Ii
    ## 2176                     MICHAUD,MARY DAVIS           Faculty Associate
    ## 2177                           MICHELS,TONY                   Professor
    ## 2178                          MICHINI,CARLA         Assistant Professor
    ## 2179                  MICKELSON,JAMIE IRENE                    Lecturer
    ## 2180                       MIDDLECAMP,CATHY                   Professor
    ## 2181                     MIER-CRUZ,BENJAMIN         Assistant Professor
    ## 2182                         MIERNOWSKA,EWA             Senior Lecturer
    ## 2183                         MIERNOWSKI,JAN                   Professor
    ## 2184                       MIKKELSON,ANDREW         Assoc Faculty Assoc
    ## 2185                     MILENKOVIC,PAUL H.         Associate Professor
    ## 2186                         MILES,KELSEY C              Assoc Lecturer
    ## 2187                         MILICIC,SRDJAN         Assoc Faculty Assoc
    ## 2188                       MILKOWSKI,ANDREW           Adjunct Professor
    ## 2189                       MILLER,BARTON P.                   Professor
    ## 2190                          MILLER,DENNIS                   Professor
    ## 2191                            MILLER,ERIC                    Lecturer
    ## 2192                        MILLER,FRANKLIN         Associate Professor
    ## 2193                           MILLER,JAMES           Faculty Associate
    ## 2194                           MILLER,JANEL                    Lecturer
    ## 2195                        MILLER,JOSEPH S                   Professor
    ## 2196                         MILLER,MICHAEL       Honorary Assoc/Fellow
    ## 2197                         MILLER,PAUL E.          Clinical Professor
    ## 2198                         MILLER,PETER M                   Professor
    ## 2199                             MILLS,NEIL         Assistant Professor
    ## 2200                            MILTON,ROSS         Assistant Professor
    ## 2201                            MIN,SANGKEE         Assistant Professor
    ## 2202                 MINI,DARSHANA SREEDHAR         Assistant Professor
    ## 2203             MINICHIELLO,VINCENT JOSEPH        Asst Professor (Chs)
    ## 2204                          MINTZ,YONATAN         Assistant Professor
    ## 2205                       MIRANDA,ALMITA A         Assistant Professor
    ## 2206                MIRSHARIFI,FATEMEHSADAT                    Lecturer
    ## 2207                         MISEY,ROBERT J          Adjunct Instructor
    ## 2208                   MISSION,PAIGE LAUREN                    Lecturer
    ## 2209                                MITCH,-          Clinical Professor
    ## 2210                     MITCHELL,CAROL K C       Assoc Professor (Chs)
    ## 2211                     MITCHELL,EVERETT D          Adjunct Instructor
    ## 2212                           MITCHELL,MEG         Associate Professor
    ## 2213                          MITCHELL,PAUL                   Professor
    ## 2214                         MITCHELL,SUSAN              Assoc Lecturer
    ## 2215                           MITMAN,GREGG                   Professor
    ## 2216                       MIYAMOTO,SHIGEKI                   Professor
    ## 2217                     MIYASAKI,JAN KEIKO             Senior Lecturer
    ## 2218                        MLADENOFF,DAVID              Professor Emer
    ## 2219                           MOBLEY,SCOTT         Assoc Faculty Assoc
    ## 2220                     MOEDERSHEIM,SABINE         Associate Professor
    ## 2221                        MOELLER,KATHRYN         Assistant Professor
    ## 2222                         MOHAMED,MAHA A       Assoc Professor (Chs)
    ## 2223                     MOHAMMADI,ABDOLLAH          Asst Faculty Assoc
    ## 2224                              MOHR,EMMA         Assistant Professor
    ## 2225                            MOK,LUCILLE                    Lecturer
    ## 2226                 MOLFENTER,NANCY FARNON                    Lecturer
    ## 2227                     MOMMAERTS,CORINA D         Assistant Professor
    ## 2228                    MOMONT,HARRY WALTER         Clinical Assoc Prof
    ## 2229                        MONAHAN,LAURA A                    Lecturer
    ## 2230                        MONETTE,RICHARD                   Professor
    ## 2231                     MONIZ,DANTIEL WYNN          Asst Faculty Assoc
    ## 2232                          MONSON,MORGAN              Assoc Lecturer
    ## 2233                       MONTGOMERY,KITTY         Assistant Professor
    ## 2234                     MOONEY,MARGARET E.              Assoc Lecturer
    ## 2235                           MOORE,DARCIE         Assistant Professor
    ## 2236                            MOORE,LUCAS              Assoc Lecturer
    ## 2237                          MOORE,SARAH A         Associate Professor
    ## 2238                        MORALES,ALFONSO                   Professor
    ## 2239                            MOREAU,PAGE                   Professor
    ## 2240                       MORELLO,SAMANTHA         Clinical Assoc Prof
    ## 2241                           MORENO,MARIA           Faculty Associate
    ## 2242                   MORENO,MEGAN ANDREAS                   Professor
    ## 2243                      MORGAN,COURTNEY E        Asst Professor (Chs)
    ## 2244                            MORGAN,DANE                   Professor
    ## 2245                      MORGAN,MICHAEL C.                   Professor
    ## 2246                             MORI,JUNKO                   Professor
    ## 2247                       MORITZ,DEBORAH C             Senior Lecturer
    ## 2248                          MORRIS,JEREMY         Associate Professor
    ## 2249                           MORRIS,MARIO                    Lecturer
    ## 2250                         MORRIS,ZACHARY         Assistant Professor
    ## 2251                  MORRISON,MOSI ADESINA         Assistant Professor
    ## 2252                       MORROW,KATHERINE         Associate Professor
    ## 2253                           MOSER,AMY R.         Associate Professor
    ## 2254                            MOSES,TALLY         Associate Professor
    ## 2255                        MOSHER,DEANE F.                   Professor
    ## 2256                       MOSKOWITZ,MARINA                   Professor
    ## 2257                             MOTT,DAVID                   Professor
    ## 2258   MOUGOUE,JACQUELINE-BETHEL KEUTCHEMEN         Assistant Professor
    ## 2259                     MOUNTAIN,ALEXANDRA              Assoc Lecturer
    ## 2260                            MOWAT,FREYA         Assistant Professor
    ## 2261                 MUEHRER,REBECCA JEANNE         Assistant Professor
    ## 2262                       MUELLER,CARLYN O         Assistant Professor
    ## 2263                MUELLER,KIMBERLY DIGGLE         Assistant Professor
    ## 2264                             MUIR,PETER                   Professor
    ## 2265                        MUKHERJEE,ANITA         Assistant Professor
    ## 2266                        MUKHERJEE,PRIYA         Assistant Professor
    ## 2267                          MUKHIN,DMITRY         Assistant Professor
    ## 2268                           MULLAHY,JOHN                   Professor
    ## 2269                    MULLEN,JESS MATTHEW           Faculty Associate
    ## 2270                    MULLEN,KEVIN GEORGE         Assistant Professor
    ## 2271                       MULVIHILL,JOHN F             Senior Lecturer
    ## 2272                      MUNCHMEYER,MORITZ         Assistant Professor
    ## 2273                    MUNIAGURRIA,MARIA E           Faculty Associate
    ## 2274                    MUNSTERMAN,AMELIA S          Clinical Asst Prof
    ## 2275              MURCHISON,MELANIE JANELLE                    Lecturer
    ## 2276                             MURPHY,JEN                    Lecturer
    ## 2277                            MURPHY,JOHN           Faculty Associate
    ## 2278                    MURPHY,PATRICK ALAN                    Lecturer
    ## 2279                          MURPHY,REGINA                   Professor
    ## 2280                       MURPHY,WILLIAM L                   Professor
    ## 2281                  MURRAY,MICHELLE RENEE              Assoc Lecturer
    ## 2282                          MURRAY,MURRAY           Faculty Associate
    ## 2283                           MURTHY,VIREN         Associate Professor
    ## 2284                        MUSTAFA,MUSTAFA           Faculty Associate
    ## 2285                            MUTLU,BILGE         Associate Professor
    ## 2286                       MUYOLEMA,ARMANDO                    Lecturer
    ## 2287                   MYERS,MARY ELIZABETH             Senior Lecturer
    ## 2288                        MYERSON,REBECCA         Assistant Professor
    ## 2289                    MYRZABEKOVA,RAUSHAN             Senior Lecturer
    ## 2290                  NACEWICZ,BRENDON MARK         Assistant Professor
    ## 2291                             NACK,JAMIE            Sr Outreach Spec
    ## 2292      NACKERS,KIRSTIN ANDREA MUEHLBAUER        Asst Professor (Chs)
    ## 2293                          NADLER,STEVEN                   Professor
    ## 2294                      NAGEL,NICHOLAS J.                    Lecturer
    ## 2295                      NAKADA,STEPHEN Y.                   Professor
    ## 2296                        NAKAKUBO,TAKAKO         Assoc Faculty Assoc
    ## 2297                      NAPARSTEK,MICHAEL                    Lecturer
    ## 2298                  NAPIERALSKI,STEPHANIE              Assoc Lecturer
    ## 2299                         NARDI,HENRIQUE                    Lecturer
    ## 2300                        NATHAN,MITCHELL                   Professor
    ## 2301                   NATHANSON,GILBERT M.                   Professor
    ## 2302                          NAUGHTON,LISA                   Professor
    ## 2303                        NAVSARIA,DIPESH       Assoc Professor (Chs)
    ## 2304                      NAWYN,KIMBERLEE H                    Lecturer
    ## 2305                       NAZAROVA,GULNISA             Senior Lecturer
    ## 2306                        NECKAR,AMANDA L          Asst Faculty Assoc
    ## 2307                             NEGRUT,DAN                   Professor
    ## 2308                 NELLIS,GREGORY FRANCIS                   Professor
    ## 2309                      NELLIS,MARGARET J       Sr Student Serv Coord
    ## 2310                       NELSESTUEN,GRANT         Associate Professor
    ## 2311                            NELSON,ADAM                   Professor
    ## 2312                            NELSON,ADAM                    Lecturer
    ## 2313                         NELSON,CONOR R         Assistant Professor
    ## 2314                           NELSON,DAVID                    Lecturer
    ## 2315                     NELSON,EVAN OTHMER        Asst Professor (Chs)
    ## 2316                    NELSON,GUNTHER PAUL                    Lecturer
    ## 2317                            NELSON,JEFF          Asst Faculty Assoc
    ## 2318                        NELSON,JENNIFER         Assistant Professor
    ## 2319                            NELSON,JOHN           Adjunct Professor
    ## 2320                       NELSON,NICOLE C.         Associate Professor
    ## 2321                           NELSON,SUSAN       Sr Student Serv Coord
    ## 2322                           NELSON,TRACY          Adjunct Instructor
    ## 2323                          NEMET,GREGORY                   Professor
    ## 2324                           NESPER,LARRY                   Professor
    ## 2325                       NESTERCHOUK,ANYA             Senior Lecturer
    ## 2326                      NETT,JENIEL EMILY         Associate Professor
    ## 2327                  NEUHAUSER,HEIDI MARIE         Clinical Instructor
    ## 2328                       NEUMANN,DONNA M.         Associate Professor
    ## 2329                     NEUMAYER,KRISTIN M         Assoc Faculty Assoc
    ## 2330                        NEVILLE,LEONORA                   Professor
    ## 2331                             NEVIN,JACK              Professor Emer
    ## 2332                NEWBURY,SANDRA PATRICIA         Clinical Assoc Prof
    ## 2333                       NEWMAN,TODD PAUL         Assistant Professor
    ## 2334                      NEWMARK,PHILLIP A                   Professor
    ## 2335                        NEWTON,LAURIE A         Clinical Assoc Prof
    ## 2336                      NEWTON,MICHAEL A.                   Professor
    ## 2337                             NEY,DENISE                   Professor
    ## 2338                        NEYRAT,FREDERIC         Associate Professor
    ## 2339                      NGOLA,AMANDA JEAN          Clinical Asst Prof
    ## 2340                    NGUYEN THI,MINHHIEN              Assoc Prof L/I
    ## 2341                            NGUYEN,BETH                   Professor
    ## 2342                             NI,CHAOQUN         Assistant Professor
    ## 2343               NICHELASON,AMY ELIZABETH          Clinical Asst Prof
    ## 2344                       NICHOLS,KATHLEEN         Assoc Faculty Assoc
    ## 2345                     NICKELLS,ROBERT W.                   Professor
    ## 2346                          NICKOLAI,ANNA                    Lecturer
    ## 2347                       NIEDENTHAL,PAULA                   Professor
    ## 2348                         NIENHUIS,JAMES                   Professor
    ## 2349                             NILI,YARON         Assistant Professor
    ## 2350              NIMITYONGSKUL,SONNY AARON         Assoc Faculty Assoc
    ## 2351                          NIMUNKAR,AMIT           Faculty Associate
    ## 2352                           NIWOT,MELODY         Assoc Faculty Assoc
    ## 2353                             NIX,ROBERT         Associate Professor
    ## 2354                        NIZIOLEK,CARRIE         Assistant Professor
    ## 2355                 NOBLES,JENNA ELIZABETH                   Professor
    ## 2356                         NOGUERA,DANIEL                   Professor
    ## 2357                 NORDER-BRANDLI,CHANDRA         Clinical Assoc Prof
    ## 2358                          NORMAN,CORRIE           Faculty Associate
    ## 2359                   NOSEK,JOSEPH MICHAEL           Faculty Associate
    ## 2360                           NOTARO,KELLI          Clinical Asst Prof
    ## 2361                          NOTBOHM,JACOB         Assistant Professor
    ## 2362                     NOWAK,ROBERT DAVID                   Professor
    ## 2363                            NOYCE,DAVID                   Professor
    ## 2364                           NTAMBI,JAMES                   Professor
    ## 2365                         NUCKOLLS,TERRY             Senior Lecturer
    ## 2366                            NYHART,LYNN                   Professor
    ## 2367                          O BRIEN,JERRY           Faculty Associate
    ## 2368                             OAKES,GALE           Faculty Associate
    ## 2369                           OAKLEY,JASON                    Lecturer
    ## 2370                    OAKLEY,LINDA DENISE                   Professor
    ## 2371                         OBERSTAR,ERICK         Assoc Faculty Assoc
    ## 2372                             OBRIEN,ANN                Dis Lecturer
    ## 2373                          OBRIEN,DANA R         Clinical Assoc Prof
    ## 2374                OCALLAGHAN,ELIZABETH M.                    Lecturer
    ## 2375                      OCONNELL,DANIEL M        Asst Professor (Chs)
    ## 2376                         OCONNOR,ANNE M       Assoc Professor (Chs)
    ## 2377                       OCONNOR,DAVID H.                   Professor
    ## 2378                    OCONNOR,SHELBY LYNN         Associate Professor
    ## 2379                          ODEGARD,LYDIA        Assoc Stu Serv Coord
    ## 2380                             ODELL,LUKE              Assoc Lecturer
    ## 2381                         ODORICO,JON S.                   Professor
    ## 2382                        OESTE,ANDREAS A           Adjunct Asst Prof
    ## 2383                            OETZEL,GARY                   Professor
    ## 2384                       OGRAS,UMIT YUSUF         Associate Professor
    ## 2385                        OGUINN,THOMAS C                   Professor
    ## 2386                             OH,EUN SIL         Assistant Professor
    ## 2387                            OH,JUNG SUN             Senior Lecturer
    ## 2388                              OHM,BRIAN                   Professor
    ## 2389                         OHNESORGE,JOHN                   Professor
    ## 2390                         OKONKWO,OZIOMA         Associate Professor
    ## 2391                          OLANIYAN,MOJI            Assistant Dean/M
    ## 2392                      OLDS,KRISTOPHER N                   Professor
    ## 2393                          OLEARY,RENAGH          Clinical Asst Prof
    ## 2394                    OLEINIK,MARK GEORGE           Adjunct Professor
    ## 2395                            OLIVE,PEGGY            Sr Outreach Spec
    ## 2396                       OLIVER,PAMELA E.                   Professor
    ## 2397                        OLIVER,THOMAS R                   Professor
    ## 2398                    OLLIVETT,TERRI LYNN         Assistant Professor
    ## 2399                    OLSEN,CHRISTOPHER W              Professor Emer
    ## 2400                          OLSON,CHRISTA         Associate Professor
    ## 2401                          OLSON,JOHN L.  Clinical Adjunct Professor
    ## 2402                         OLSON,LEAH JOY              Assoc Prof L/I
    ## 2403                             OLSON,MARK           Faculty Associate
    ## 2404                            OLSON,TRENT                    Lecturer
    ## 2405                          OLSZEWSKI,DAN           Faculty Associate
    ## 2406                      ONELLION,MARSHALL                   Professor
    ## 2407                      ONG,IRENE MAY LIN         Assistant Professor
    ## 2408                      OOSTERWYK,JOHANNA           Faculty Associate
    ## 2409                           ORLOV,DMITRY         Assistant Professor
    ## 2410                          OROURKE,ANN P       Assoc Professor (Chs)
    ## 2411                   OROURKE,BERNADETT M.            Sr Outreach Spec
    ## 2412                              ORR,SARAH          Clinical Professor
    ## 2413                          ORROCK,JOHN L                   Professor
    ## 2414                     ORTIZ-ROBLES,MARIO                   Professor
    ## 2415                      OSBORNE,CHARLES A          Clinical Asst Prof
    ## 2416                    OSORIO,JORGE EMILIO                   Professor
    ## 2417                         OSPOVAT,KIRILL         Assistant Professor
    ## 2418                   OSSORIO,PILAR NICOLE                   Professor
    ## 2419                            OSSWALD,TIM                   Professor
    ## 2420                          OTEGUI,MARISA                   Professor
    ## 2421                      OTEPKA,CARRIE ANN          Clinical Asst Prof
    ## 2422                          OTTMANN,SUSAN           Faculty Associate
    ## 2423                             OTTO,MARIO         Associate Professor
    ## 2424                           OTTO,STACY B         Clinical Instructor
    ## 2425                   OUAYOGODE,MARIETOU H         Assistant Professor
    ## 2426                           OW,TERENCE T         Visiting Assoc Prof
    ## 2427                  OWENBY,THOMAS CLINTON           Faculty Associate
    ## 2428                             OWENS,RYAN                   Professor
    ## 2429              OWUSU-YEBOA,LATISH CHERIE                    Lecturer
    ## 2430                          OZDOGAN,MUTLU         Associate Professor
    ## 2431                            PAC,GREGORY             Senior Lecturer
    ## 2432                            PAC,JESSICA         Assistant Professor
    ## 2433                        PACHECO,MARIANA         Associate Professor
    ## 2434                          PADILLA,DARCY         Associate Professor
    ## 2435                       PAGE JR.,C DAVID                   Professor
    ## 2436                        PAGEL,HOLLY RAE         Assoc Faculty Assoc
    ## 2437                        PAGLIARINI,DAVE         Assistant Professor
    ## 2438                        PAKER,BULENT S.          Clinical Professor
    ## 2439                    PAKES AHLMAN,ANGELA                  Researcher
    ## 2440                           PALECEK,SEAN                   Professor
    ## 2441                  PALLADINO,KIMBERLY J.         Assistant Professor
    ## 2442                   PALMENBERG,ANN CAROL                   Professor
    ## 2443                 PALMER,KASSANDRA BOEHM                    Lecturer
    ## 2444                         PALMER,LINDSAY         Associate Professor
    ## 2445                   PALMER,MARISA MACKEY             Senior Lecturer
    ## 2446                       PALMQUIST,RUTH A             Senior Lecturer
    ## 2447                            PALTA,JIWAN                   Professor
    ## 2448                            PAN,WENXIAO         Assistant Professor
    ## 2449                               PAN,XUAN         Associate Professor
    ## 2450                             PAN,XUEJUN                   Professor
    ## 2451                              PAN,YIBIN         Associate Professor
    ## 2452                          PAN,ZHONGDANG                   Professor
    ## 2453                         PANDEY,NANDINI         Associate Professor
    ## 2454                  PANKOW,BENJAMIN JACOB        Asst Prof Of Mil Sci
    ## 2455                        PANZER,SARAH E.         Assistant Professor
    ## 2456                PAPAILIOPOULOS,DIMITRIS         Assistant Professor
    ## 2457                            PAPE,LOUISE            Senior Scientist
    ## 2458                            PAPP,LAUREN                   Professor
    ## 2459                        PARETSKAYA,ANNA                    Lecturer
    ## 2460                             PARINS,AMY          Clinical Asst Prof
    ## 2461                        PARISI,GIUSTINA                    Lecturer
    ## 2462                               PARK,JIM                   Professor
    ## 2463                         PARKER,DOMINIC         Associate Professor
    ## 2464                            PARKER,JEFF         Assistant Professor
    ## 2465                         PARKIN,KIRK L.              Professor Emer
    ## 2466                            PARKS,BRIAN         Assistant Professor
    ## 2467               PARRA-MONTESINOS,GUSTAVO                   Professor
    ## 2468                            PARRELL,BEN         Assistant Professor
    ## 2469                        PARRISH,JOHN J.                   Professor
    ## 2470                        PASKEWITZ,SUSAN                   Professor
    ## 2471                      PATANKAR,MANISH S                   Professor
    ## 2472                             PATEL,GINA          Adjunct Assoc Prof
    ## 2473                 PATEL,JIGNESH MANUBHAI                   Professor
    ## 2474                            PATEL,VIVAK         Assistant Professor
    ## 2475                        PATENAUDE,LOUKA                    Lecturer
    ## 2476                      PATTNAIK,BIKASH R         Assistant Professor
    ## 2477                            PATZ,JEAN A                    Lecturer
    ## 2478                          PATZ,JONATHAN                   Professor
    ## 2479                            PAUL,SEAN T                   Professor
    ## 2480                          PAULEY,GWYN C              Assoc Lecturer
    ## 2481                           PAULI,DENNIS                    Lecturer
    ## 2482                         PAULI,JONATHAN         Associate Professor
    ## 2483                           PAULSEN,KURT                   Professor
    ## 2484                       PAUSTIAN,TIMOTHY       Dis Faculty Associate
    ## 2485                           PAVEK, KATIE         Clinical Instructor
    ## 2486                    PAWLAK,ROBERTA PAGE          Clinical Professor
    ## 2487                           PAYSEUR,BRET                   Professor
    ## 2488                            PAZICNI,SAM         Assistant Professor
    ## 2489                    PEARCE,ROBERT ALLEN                   Professor
    ## 2490                          PEARSON,ALICE         Clinical Assoc Prof
    ## 2491                        PECANAC,KRISTEN         Assistant Professor
    ## 2492                        PECARINA,JOHN M        Professor Of Mil Sci
    ## 2493                             PECK,JOANN         Associate Professor
    ## 2494                        PEDERSEN,JOEL A                   Professor
    ## 2495              PEDRIANA,NICHOLAS ANTHONY             Senior Lecturer
    ## 2496                        PEEBLES,PATRICK          Clinical Asst Prof
    ## 2497                            PEEK,AUDREY                    Lecturer
    ## 2498                          PEEK,SIMON F.          Clinical Professor
    ## 2499                                PEERY,M                   Professor
    ## 2500                        PEHAR,MARIANA A         Assistant Professor
    ## 2501                    PELEGRI,FRANCISCO J                   Professor
    ## 2502                     PELLEGRINI,MARCELO         Associate Professor
    ## 2503                        PELLETIER,DAVID                    Lecturer
    ## 2504                 PELLIN,MACKENZIE ARLAH          Clinical Asst Prof
    ## 2505                 PENAGARICANO,FRANCISCO         Assistant Professor
    ## 2506                                PENG,XU                    Lecturer
    ## 2507                              PENG,ZHAO              Assoc Lecturer
    ## 2508                         PENNELLA,MARIO         Assoc Faculty Assoc
    ## 2509                        PEPPARD,PAUL E.                   Professor
    ## 2510                    PEPPERELL,CAITLIN S         Associate Professor
    ## 2511                         PEREPEZKO,JOHN                   Professor
    ## 2512                         PERGAMENT,ADAM             Senior Lecturer
    ## 2513                        PERNA,NICOLE T.                   Professor
    ## 2514                            PERRY,DAVID                   Professor
    ## 2515                      PERSIKE,CONSTANCE         Clinical Assoc Prof
    ## 2516                      PESAVENTO,THERESA                    Lecturer
    ## 2517                           PETER,KIRK A           Faculty Associate
    ## 2518                        PETERS,DONNA M.                   Professor
    ## 2519                         PETERS,JASON M         Assistant Professor
    ## 2520                        PETERS,SHANAN E                   Professor
    ## 2521               PETERSON,AMY LYNN HERING       Assoc Professor (Chs)
    ## 2522                           PETERSON,KIM             Senior Lecturer
    ## 2523                       PETERSON,MICHAEL                   Professor
    ## 2524                       PETERSON,SANDY K              Assoc Lecturer
    ## 2525                       PETTERSEN,CLAIRE              Assoc Lecturer
    ## 2526                  PETTY,ELIZABETH MARIE                   Professor
    ## 2527                          PETTY,GRANT W                   Professor
    ## 2528                          PEVEHOUSE,JON                   Professor
    ## 2529                 PEYER,SUZANNE MICHELLE              Assoc Lecturer
    ## 2530                      PFEFFERKORN,FRANK                   Professor
    ## 2531                          PFLEGER,BRIAN                   Professor
    ## 2532                         PFLUM,MADELINE              Assoc Lecturer
    ## 2533                       PFOTENHAUER,JOHN                   Professor
    ## 2534                         PHANEUF,DANIEL                   Professor
    ## 2535                          PHELPS,ALYSSA                    Lecturer
    ## 2536                  PHELPS,KATHERINE ANNE                    Lecturer
    ## 2537                  PHILLIPPI,ERIC THOMAS  Clinical Adjunct Asst Prof
    ## 2538                          PHILLIPS,GENE                   Professor
    ## 2539                     PHILLIPS,MEGAN ANN          Adjunct Instructor
    ## 2540                 PHILLIPS-COURT,KRISTIN         Associate Professor
    ## 2541                 PICASSO RISSO,VALENTIN         Assistant Professor
    ## 2542               PICCIONE,MICHELLE LAUREN         Clinical Instructor
    ## 2543                 PICKERING,TRAVIS RAYNE                   Professor
    ## 2544                            PICKETT,DAN             Senior Lecturer
    ## 2545                 PICKETT,KRISTEN ALEXIS         Assistant Professor
    ## 2546                           PIDGEON,ANNA                   Professor
    ## 2547                           PIERCE,DEBRA           Faculty Associate
    ## 2548                  PIERCE,ROBERT BRADLEY                   Professor
    ## 2549                    PIERCE,TIMOTHY JOHN          Adjunct Instructor
    ## 2550                          PIKE,J WESLEY                   Professor
    ## 2551                    PILIAVIN,JANE ALLYN              Professor Emer
    ## 2552                     PILLAI,PARVATHY T.        Asst Professor (Chs)
    ## 2553                PIMENTEL ALARCON,DANIEL         Assistant Professor
    ## 2554                             PINC,GUZZO                    Lecturer
    ## 2555                       PINCHEIRA,JOSE A         Associate Professor
    ## 2556                   PINEKENSTEIN,BARBARA          Clinical Professor
    ## 2557                      PINKERTON,MARIE E         Clinical Assoc Prof
    ## 2558                     PIRE,TIMOTHY JAMES                    Lecturer
    ## 2559                       PITT,MECHELE LEE                    Lecturer
    ## 2560                       PITTERLE,MICHAEL       Assoc Professor (Chs)
    ## 2561                    PLANTE,DAVID THOMAS         Assistant Professor
    ## 2562                       PLANTE,SEBASTIEN         Assistant Professor
    ## 2563                        PLANTS,JENNIFER           Faculty Associate
    ## 2564                         PLUMMER,BRENDA                   Professor
    ## 2565                            POE,CYNTHIA         Assoc Faculty Assoc
    ## 2566                     POE-GAVLINSKI,RYAN         Clinical Instructor
    ## 2567                   POEHLMANN,JULIE ANNE                   Professor
    ## 2568                          POINTON,LUCAS                    Lecturer
    ## 2569                   POLFUSS,MICHELE LYNN           Faculty Associate
    ## 2570                            POLLAK,SETH                   Professor
    ## 2571                            POLMAN,EVAN         Associate Professor
    ## 2572                     POLTORATSKI,ALEXEI                   Professor
    ## 2573                           POMPEY,COREY         Assoc Faculty Assoc
    ## 2574                    PONIK,SUZANNE MARIE         Assistant Professor
    ## 2575                            PONTO,KEVIN         Associate Professor
    ## 2576                            POOL,JOHN E         Associate Professor
    ## 2577                         POORE,SAMUEL O         Associate Professor
    ## 2578                       POPKEWITZ,THOMAS                   Professor
    ## 2579                        POPULIN,LUIS C.                   Professor
    ## 2580                          PORTER,ANDREA       Assoc Professor (Chs)
    ## 2581                      PORTER,JACK R. II                   Professor
    ## 2582                      PORTILLO,EDWARD C        Asst Professor (Chs)
    ## 2583                           POSEN,HART E                   Professor
    ## 2584                      POSEY-MADDOX,LINN         Associate Professor
    ## 2585                            POSTLE,BRAD                   Professor
    ## 2586                     POTTER,HEATHER A D       Assoc Professor (Chs)
    ## 2587                         POTTER,KENNETH                   Professor
    ## 2588                          POULOS,ANDREA           Faculty Associate
    ## 2589                   POULSEN,KEITH PAPPAS         Clinical Assoc Prof
    ## 2590                         POWELL,ELEANOR         Associate Professor
    ## 2591                         POWELL,LINDSEY          Adjunct Instructor
    ## 2592                          POWERS,ALEXIS         Clinical Instructor
    ## 2593                       PRABHAKAR,PAVANA         Assistant Professor
    ## 2594                      PRABHAKARAN,VIVEK         Associate Professor
    ## 2595                         PRASCH,ALLISON         Assistant Professor
    ## 2596                             PREM,KATHY         Assoc Faculty Assoc
    ## 2597                         PRESTON,DANIEL         Assistant Professor
    ## 2598                            PRICE,BRIAN           Adjunct Asst Prof
    ## 2599                         PRIMM,STEFANIE          Asst Faculty Assoc
    ## 2600                           PRIMUS,ROY J           Adjunct Asst Prof
    ## 2601                           PRINGLE,ANNE                   Professor
    ## 2602                      PRITCHARD,JESSICA          Clinical Asst Prof
    ## 2603                   PROLLA,TOMAS ALBERTO                   Professor
    ## 2604                            PROST,LYNNE           Faculty Associate
    ## 2605                        PROVENCHER,BILL                   Professor
    ## 2606                        PRUITT,JENNIFER         Associate Professor
    ## 2607                             PRYDE,EMMA                    Lecturer
    ## 2608                   PUCCINELLI,JOHN PAUL           Faculty Associate
    ## 2609                  PUCCINELLI,TRACY JANE         Assoc Faculty Assoc
    ## 2610                        PUGLIELLI,LUIGI                   Professor
    ## 2611                          PUJARA,NIMISH         Assistant Professor
    ## 2612                              PUJOL,EVE           Faculty Associate
    ## 2613                  PULIA,MICHAEL SANTINO         Assistant Professor
    ## 2614                           PULIA,NICOLE         Assistant Professor
    ## 2615                  PULTORAK,JOSHUA DAVID           Faculty Associate
    ## 2616                         PULTORAK,SARAH           Faculty Associate
    ## 2617                    PUNTAMBEKAR,SADHANA                   Professor
    ## 2618                          PURDUE,EUGENE           Faculty Associate
    ## 2619                            PURNELL,TOM                   Professor
    ## 2620                   PUSTEJOVSKY,JAMES E.         Associate Professor
    ## 2621                       PUTNAM,WILLIAM C          Visiting Professor
    ## 2622                          QIAN,XIAOPING                   Professor
    ## 2623                              QIN,MOHAN         Assistant Professor
    ## 2624                      QUAGLIANA,CHARLES           Adjunct Professor
    ## 2625                        QUANBECK,ANDREW         Assistant Professor
    ## 2626                        QUARLES,BRANDON              Assoc Lecturer
    ## 2627                      QUILLEN,CAITLIN M                    Lecturer
    ## 2628                      QUINN,DAVEN PATEL              Assoc Lecturer
    ## 2629                         QUINN,MICHELLE          Clinical Professor
    ## 2630                              QUINT,DAN         Associate Professor
    ## 2631                         QUINTANA,STEVE                   Professor
    ## 2632                          QUINTIN,ERWAN                   Professor
    ## 2633                  QURAISHI-LANDES,ASIFA                   Professor
    ## 2634                       QURESHI,ARIF ALI             Senior Lecturer
    ## 2635                          RACETTE,MOLLY          Clinical Asst Prof
    ## 2636          RACINE GILLES,CAROLINE NICOLE         Assoc Faculty Assoc
    ## 2637                        RADELOFF,VOLKER                   Professor
    ## 2638                          RADWIN,ROBERT                   Professor
    ## 2639                              RAE,JULIE          Admin Program Spec
    ## 2640                     RAHOI,DANE MICHAEL         Clinical Instructor
    ## 2641                       RAIFE,THOMAS JAY             Professor (Chs)
    ## 2642                     RAIMBEKOVA,LOLAGUL                    Lecturer
    ## 2643                             RAIMY,ERIC                   Professor
    ## 2644                         RAISON,CHARLES                   Professor
    ## 2645                 RAKOTONDRAFARA,AURELIE         Associate Professor
    ## 2646                     RALPHE,JOHN CARTER         Associate Professor
    ## 2647                           RAMAN,VATSAN         Assistant Professor
    ## 2648                     RAMANATHAN,PARMESH                   Professor
    ## 2649                RAMBERG,ERICA ELIZABETH         Assoc Faculty Assoc
    ## 2650           RAMIREZ TAHUADO,MARLA ANDREA         Assistant Professor
    ## 2651                       RAMIREZ,ALYSSA M          Clinical Asst Prof
    ## 2652                           RAMLY,EDMOND         Assistant Professor
    ## 2653                         RAMOS,MICHELLE              Assoc Lecturer
    ## 2654                                RAN,BIN                   Professor
    ## 2655                          RANADE,MILIND             Senior Lecturer
    ## 2656                   RANALLO,FRANK NUNZIO             Professor (Chs)
    ## 2657                           RANHEIM,ERIK             Professor (Chs)
    ## 2658                             RANK,DAVID          Adjunct Assoc Prof
    ## 2659                         RANKIN,SCOTT A                   Professor
    ## 2660                            RAO,LUDMILA             Senior Lecturer
    ## 2661                            RAO,RAJIV G         Associate Professor
    ## 2662                      RASCHKA,SEBASTIAN         Assistant Professor
    ## 2663                       RASKUTTI,GARVESH         Associate Professor
    ## 2664                        RATLIFF,CAMERON         Clinical Instructor
    ## 2665                        RATNER,JENNIFER                   Professor
    ## 2666                 RATTERMAN,DENISE MARIE           Faculty Associate
    ## 2667                            RAU,MARTINA         Associate Professor
    ## 2668                            RAVAL,AMISH         Associate Professor
    ## 2669                           RAYMENT,IVAN                   Professor
    ## 2670                 REARDON,CLAUDIA LOUISE       Assoc Professor (Chs)
    ## 2671                            REARDON,JIM           Faculty Associate
    ## 2672                            REBEL,BRIAN         Associate Professor
    ## 2673                    REBOUCAS DOREA,JOAO         Assistant Professor
    ## 2674                              RECK,TODD                    Lecturer
    ## 2675                    RECORD JR.,M THOMAS                   Professor
    ## 2676               RED EAGLE,LAURA CANDIDIA              Assoc Lecturer
    ## 2677                REDFIELD III,ROBERT RAY       Honorary Assoc/Fellow
    ## 2678                          REED,JENNIFER                   Professor
    ## 2679                           REED,JESS D.                   Professor
    ## 2680                         REEDER,SCOTT B                   Professor
    ## 2681                          REESE,WILLIAM                   Professor
    ## 2682                      REILLY,MEGAN MARY         Assistant Professor
    ## 2683                         REINDL,DOUGLAS                   Professor
    ## 2684                         REINEMANN,DOUG                   Professor
    ## 2685                    REINFELDT,DIANE LOU         Clinical Assoc Prof
    ## 2686                       REINHOLTZ,RHONDA             Senior Lecturer
    ## 2687                       REISER,CATHERINE             Professor (Chs)
    ## 2688                   REKATSINAS,THEODOROS         Assistant Professor
    ## 2689                          REMALIA,MAREE              Assoc Lecturer
    ## 2690             REMINGTON,PATRICK LHEUREUX              Professor Emer
    ## 2691                 REMOND-TIEDREZ,ANTOINE          Visiting Asst Prof
    ## 2692                        REMUCAL,CHRISTY         Associate Professor
    ## 2693                           RENAULT,MARC          Asst Faculty Assoc
    ## 2694                       RENSHON,JONATHAN         Associate Professor
    ## 2695                              RENZ,MARK                   Professor
    ## 2696                            REPS,THOMAS                   Professor
    ## 2697                       RESNICK,DANIEL K                   Professor
    ## 2698                           REY,FEDERICO         Associate Professor
    ## 2699                          REYES,LETICIA         Assistant Professor
    ## 2700                        REYNOLDS,ANDREW         Associate Professor
    ## 2701                    REYNOLDS,MATTHEW R.         Assistant Professor
    ## 2702                                RHA,EUN              Assoc Lecturer
    ## 2703                        RHODES,DANIEL A         Assistant Professor
    ## 2704                        RICE,GREGORY M.       Assoc Professor (Chs)
    ## 2705                            RICE,JOHN P       Assoc Professor (Chs)
    ## 2706                      RICH,WALTER HENRY           Faculty Associate
    ## 2707                          RICHARDS,CATE                    Lecturer
    ## 2708                        RICHARDS,MARK P                   Professor
    ## 2709                      RICHARDSON,ANGELA         Assoc Faculty Assoc
    ## 2710                          RICHERT,LUCAS         Associate Professor
    ## 2711                      RICHMAN,MICHAEL P          Adjunct Instructor
    ## 2712                    RICK,STEVEN WILLIAM             Senior Lecturer
    ## 2713                        RICKE,STEVEN C.                   Professor
    ## 2714                             RICKE,WILL                   Professor
    ## 2715                        RICKENBACH,MARK                   Professor
    ## 2716                      RIDDIOUGH,TIMOTHY                   Professor
    ## 2717                           RIDDLE,KARYN                   Professor
    ## 2718                            RIDER,ROBIN             Senior Lecturer
    ## 2719                          RIDGELY,STEVE         Associate Professor
    ## 2720                       RIDGELY,SUSAN B.                   Professor
    ## 2721                        RIENSTRA,CHAD M                   Professor
    ## 2722                         RIGBY,BRITTNEY         Clinical Instructor
    ## 2723                   RILEY,CARRIE JACKSON           Faculty Associate
    ## 2724                    RINDFLEISCH,JAMES A       Honorary Assoc/Fellow
    ## 2725                             RINGE,NILS                   Professor
    ## 2726                  RINGLER,TAMSIE LOUISE                    Lecturer
    ## 2727                   RINGLER,THOR STEPHEN  Clinical Adjunct Asst Prof
    ## 2728                           RIOS,SARAH M         Assistant Professor
    ## 2729                    RIOUX,RENEE ARIELLE         Assistant Professor
    ## 2730                          RISSMAN,ADENA                   Professor
    ## 2731                          RITERS,LAUREN                   Professor
    ## 2732                           ROALD,LINE A         Assistant Professor
    ## 2733                        ROBATTO,ROBERTO         Assistant Professor
    ## 2734                        ROBB,CLIFFORD A         Associate Professor
    ## 2735                           ROBBINS,PAUL                   Professor
    ## 2736                       ROBERT,STEPHANIE                   Professor
    ## 2737                      ROBERTS,ELIZABETH         Clinical Instructor
    ## 2738                    ROBERTS,MARY LOUISE                   Professor
    ## 2739                          ROBERTS,TONYA         Assistant Professor
    ## 2740                  ROBERTSON SMITH,AMBER         Assoc Faculty Assoc
    ## 2741                      ROBERTSON,GAIL A.                   Professor
    ## 2742                       ROBERTSON,MORGAN                   Professor
    ## 2743               ROBINSON,STEPHEN MICHAEL              Professor Emer
    ## 2744                         ROBINSON,SUSAN                   Professor
    ## 2745                         ROCH,SEBASTIEN                   Professor
    ## 2746                          ROCK,AARON W.         Assistant Professor
    ## 2747                    ROCK,MICHAEL JOSEPH             Professor (Chs)
    ## 2748                       ROCK-SINGER,CARA         Assistant Professor
    ## 2749                             RODEN,ERIC                   Professor
    ## 2750                       RODGERS,LENNON P                    Lecturer
    ## 2751                  RODRIGUEZ GOMEZ,DIANA         Assistant Professor
    ## 2752                  RODRIGUEZ,JOSE ISRAEL         Assistant Professor
    ## 2753               RODRIGUEZ-GURIDI,BARBARA         Assoc Faculty Assoc
    ## 2754                          ROESSLER,JEFF             Senior Lecturer
    ## 2755                          ROGERS,JEREMY         Assistant Professor
    ## 2756                            ROGERS,JOEL                   Professor
    ## 2757                 ROGERS,KAYCEE DANIELLE           Faculty Associate
    ## 2758                       ROGERS,TIMOTHY T                   Professor
    ## 2759                              ROHE,KARL         Associate Professor
    ## 2760                         ROJAS,HERNANDO                   Professor
    ## 2761                       ROLDAN,ALEJANDRO         Assistant Professor
    ## 2762                               ROLL,JON           Faculty Associate
    ## 2763                          ROMAN,DIEGO X         Assistant Professor
    ## 2764                         ROMBACH,NICOLE                    Lecturer
    ## 2765                  ROMERO ARVELO,EDUARDO          Asst Faculty Assoc
    ## 2766                          ROMERO,PHILIP         Assistant Professor
    ## 2767                 ROMMELFAENGER,MARIJO A         Dis Professor (Chs)
    ## 2768                               RON,AMOS                   Professor
    ## 2769                        RONDON,MICHELLE           Faculty Associate
    ## 2770                            RONIS,DAVID         Assistant Professor
    ## 2771                       RONK,ERIC THOMAS          Asst Faculty Assoc
    ## 2772           RONNEKLEIV-KELLY,SEAN MARTIN         Assistant Professor
    ## 2773                       ROONEY,FRANCIS J         Assoc Faculty Assoc
    ## 2774                         ROOPRA,AVTAR S         Associate Professor
    ## 2775                          ROOS,LIINA-LY         Assistant Professor
    ## 2776                          ROOT,THATCHER                   Professor
    ## 2777                      ROS,ALEJANDRA ROS         Assistant Professor
    ## 2778          ROSA,GUILHERME J DE MAGALHAES                   Professor
    ## 2779                           ROSA,KATHY S                    Lecturer
    ## 2780              ROSADO-MENDEZ,IVAN MIGUEL         Assistant Professor
    ## 2781                            ROSE,WARREN         Associate Professor
    ## 2782                         ROSE,WILLIAM N       Assoc Professor (Chs)
    ## 2783                        ROSEN,ELIZABETH         Assoc Faculty Assoc
    ## 2784                          ROSENBERG,ARI         Assistant Professor
    ## 2785                      ROSENBERG,DOUGLAS                   Professor
    ## 2786                       ROSENBERG,MARGIE                   Professor
    ## 2787                       ROSENBLUM,JORDAN                   Professor
    ## 2788                      ROSENHAGEN,ULRICH           Faculty Associate
    ## 2789                ROSENKRANZ,MELISSA ANNE         Assistant Professor
    ## 2790                        ROSENTHAL,DAVID                   Professor
    ## 2791                           ROSIN,COOPER              Assoc Lecturer
    ## 2792                              ROSS,JEFF              Professor Emer
    ## 2793                       ROSTEK,MARZENA J                   Professor
    ## 2794                     ROTH,JOSHUA DANIEL         Assistant Professor
    ## 2795                     ROTH,ROBERT EMMETT         Associate Professor
    ## 2796                         ROTHAMER,DAVID                   Professor
    ## 2797                        ROTTMAYER,JULIA           Faculty Associate
    ## 2798                        ROTZENBERG,KATE         Assoc Faculty Assoc
    ## 2799                          ROUSE,DOUGLAS                   Professor
    ## 2800                            ROWE,ANGELA         Assistant Professor
    ## 2801                              ROWE,PAUL                   Professor
    ## 2802                ROWELL,TAWANDRA LASHONE         Assistant Professor
    ## 2803                           ROY,SUSHMITA         Associate Professor
    ## 2804                    ROYSTON,REGINOLD A.         Assistant Professor
    ## 2805                          RUARK,MATTHEW                   Professor
    ## 2806                             RUBEL,ALAN         Associate Professor
    ## 2807                         RUBIN,ANDREW M                    Lecturer
    ## 2808                         RUBIN,JENNIFER                    Lecturer
    ## 2809                           RUDOLPH,JOHN                   Professor
    ## 2810                        RUDRARAJU,SHIVA         Assistant Professor
    ## 2811                         RUDYKH,STEPHAN         Assistant Professor
    ## 2812                               RUE,ANNA          Asst Faculty Assoc
    ## 2813                               RUHL,KIM         Associate Professor
    ## 2814                              RUI,LIXIN         Associate Professor
    ## 2815                         RUMBLE,PATRICK                   Professor
    ## 2816                             RUNGE,TROY                   Professor
    ## 2817                          RUPPAR,ANDREA         Associate Professor
    ## 2818                          RUSS,ROSEMARY         Associate Professor
    ## 2819                     RUSSELL,JEFFREY S.                   Professor
    ## 2820                  RUSSELL,TIMOTHY JAMES              Assoc Lecturer
    ## 2821                         RUTECKI,TERESA                    Lecturer
    ## 2822                      RUTHERFORD,THOMAS                   Professor
    ## 2823                             RYFF,CAROL                   Professor
    ## 2824                        RYLANDER,HELENA         Clinical Assoc Prof
    ## 2825                         RZCHOWSKI,MARK                   Professor
    ## 2826                       SAALMANN,YURI B.         Associate Professor
    ## 2827                          SAATCHI,AHMAD           Faculty Associate
    ## 2828 SABAAALAZAB,MARIAM MOHAMED ALY NASHAAT                    Lecturer
    ## 2829                           SAFDAR,NASIA                   Professor
    ## 2830                           SAFFMAN,MARK                   Professor
    ## 2831                          SAFFRAN,JENNY                   Professor
    ## 2832                          SAGE,ADRIANNA          Clinical Asst Prof
    ## 2833                           SAGER,LESLEY         Assoc Faculty Assoc
    ## 2834                          SAHA,KRISHANU         Associate Professor
    ## 2835                              SALA,FRED         Assistant Professor
    ## 2836                        SALADAR,TRACY E         Clinical Assoc Prof
    ## 2837                       SALAMAT,SHAHRIAR             Professor (Chs)
    ## 2838                  SALGADO PABON,WILMARA         Assistant Professor
    ## 2839                            SALMONS,JOE                   Professor
    ## 2840                          SALO,DOROTHEA       Dis Faculty Associate
    ## 2841                     SALZMAN,TINA MARIE          Clinical Professor
    ## 2842                       SAMANTA,JAYSHREE         Assistant Professor
    ## 2843                       SAMPENE,EMMANUEL                    Lecturer
    ## 2844                        SAMPLE,SUSANNAH         Assistant Professor
    ## 2845               SANCHEZ,KATHRYN MARGARET                   Professor
    ## 2846                          SANDBO,NATHAN         Associate Professor
    ## 2847                          SANDERS,SCOTT                   Professor
    ## 2848                     SANDGREN,ERIC PAUL                   Professor
    ## 2849                     SANDLER,RICKY CHAD                    Lecturer
    ## 2850                          SANDOCK,SARAH           Adjunct Asst Prof
    ## 2851                          SANDOR,MATYAS                   Professor
    ## 2852                          SANFORD,GREGG             Senior Lecturer
    ## 2853                     SANKARALINGAM,KARU                   Professor
    ## 2854                        SANKARAN,KRIS R         Assistant Professor
    ## 2855                       SANMIGUEL,JOSHUA         Assistant Professor
    ## 2856                             SANS,ORIOL         Assistant Professor
    ## 2857                      SANTIAGO,KELVIN R         Assoc Faculty Assoc
    ## 2858                        SAPEGA,ELLEN W.                   Professor
    ## 2859                               SARADA,-         Assistant Professor
    ## 2860                             SARFF,JOHN                   Professor
    ## 2861                       SARLIOGLU,BULENT         Associate Professor
    ## 2862                          SARMADI,MAJID                   Professor
    ## 2863                     SARMIENTO,CAROLINA         Assistant Professor
    ## 2864                          SAUER,HEATHER                    Lecturer
    ## 2865                               SAUER,JD         Associate Professor
    ## 2866                        SAVER,ALEXANDER         Clinical Instructor
    ## 2867                       SCHACHTER,PARTHY             Senior Lecturer
    ## 2868                SCHAEFER,DANIEL MEILAHN                   Professor
    ## 2869                         SCHAEFER,SUSAN         Clinical Assoc Prof
    ## 2870                            SCHALK,SAMI         Associate Professor
    ## 2871                     SCHARDT,DANA ELYSE         Clinical Assoc Prof
    ## 2872                      SCHARRER,JONATHAN          Clinical Asst Prof
    ## 2873                         SCHATZKE,KYOKO         Clinical Instructor
    ## 2874                      SCHAUB,ANNA MARIE         Clinical Instructor
    ## 2875                          SCHAUER,JAMES                   Professor
    ## 2876         SCHAUMBERG,KATHERINE ELIZABETH        Asst Professor (Chs)
    ## 2877                        SCHECHTER,LAURA                   Professor
    ## 2878                        SCHECHTMAN,ANAT         Associate Professor
    ## 2879                          SCHEELE,CHRIS                    Lecturer
    ## 2880                          SCHEER,ELAINE                   Professor
    ## 2881                     SCHEND,VALERIE ANN         Clinical Instructor
    ## 2882                      SCHEUFELE,DIETRAM                   Professor
    ## 2883                       SCHIEKE,STEFAN M        Asst Professor (Chs)
    ## 2884                          SCHIFERL,RICH           Adjunct Asst Prof
    ## 2885                          SCHLOSS,KAREN         Assistant Professor
    ## 2886                  SCHMIDT,CALICO ESTHER         Clinical Instructor
    ## 2887                           SCHMIDT,J.R.                   Professor
    ## 2888                 SCHMIDT,JEFFREY ROBERT           Faculty Associate
    ## 2889                      SCHMIDT,JESSICA N        Asst Professor (Chs)
    ## 2890                           SCHMIDT,NETE           Faculty Associate
    ## 2891                          SCHMIDT,SILKE              Assoc Lecturer
    ## 2892                 SCHMIEDICKE,DAVID PAUL          Adjunct Assoc Prof
    ## 2893                            SCHMIT,JOAN                   Professor
    ## 2894                            SCHMITZ,AMY              Assoc Lecturer
    ## 2895                       SCHMITZ,LAUREN L         Assistant Professor
    ## 2896                SCHMITZ,NATALIE SUZANNE        Asst Professor (Chs)
    ## 2897                         SCHMITZ,OLIVER                   Professor
    ## 2898               SCHMITZ-SIEBERTZ,VANESSA              Assoc Lecturer
    ## 2899                    SCHNEIDER,ANNEMARIE         Associate Professor
    ## 2900                      SCHNEIDER,DAVID F         Assistant Professor
    ## 2901                            SCHNELL,LIZ         Clinical Assoc Prof
    ## 2902                       SCHNUR,ROBERT A.          Adjunct Instructor
    ## 2903                   SCHOMAKER,JENNIFER M                   Professor
    ## 2904              SCHONBERG,CHRISTINA CAROL                    Lecturer
    ## 2905                          SCHOOHS,SHARI                    Lecturer
    ## 2906                         SCHOVILLE,SEAN         Associate Professor
    ## 2907                   SCHRAGE,WILLIAM GREG                   Professor
    ## 2908                        SCHREIER,MARCEL         Assistant Professor
    ## 2909                       SCHRODI,STEVEN J         Assistant Professor
    ## 2910                   SCHROEDER,CARRIE ANN          Clinical Asst Prof
    ## 2911                         SCHROEDER,GREG             Senior Lecturer
    ## 2912                       SCHROEDER,SISSEL                   Professor
    ## 2913                       SCHROEPFER,TRACY                   Professor
    ## 2914                           SCHUBERT,AMY           Faculty Associate
    ## 2915                  SCHUCHARDT,ERIC JAMES         Assoc Faculty Assoc
    ## 2916                     SCHUCHARDT,MAKAYLA         Assoc Faculty Assoc
    ## 2917                         SCHUELKE,SHANE        Asst Prof Of Mil Sci
    ## 2918                       SCHUELLER,JEANNE           Faculty Associate
    ## 2919                       SCHULDIES,JAKE M              Assoc Lecturer
    ## 2920                        SCHULFER,NATHAN           Faculty Associate
    ## 2921                            SCHULTZ,AMY              Assoc Lecturer
    ## 2922                 SCHULTZ,KELLY KATHLEEN         Clinical Instructor
    ## 2923                       SCHUMACHER,ERICA         Clinical Instructor
    ## 2924                      SCHUSTER,JONATHAN          Adjunct Instructor
    ## 2925               SCHWARTZ,CHRISTINE RENEE                   Professor
    ## 2926                         SCHWARTZ,DAVID                   Professor
    ## 2927                      SCHWARTZ,DAVID C.                   Professor
    ## 2928                  SCHWARTZ,PAUL --SON--         Clinical Instructor
    ## 2929                      SCHWARZ,ALLISON M              Assoc Lecturer
    ## 2930                         SCHWARZ,ROBERT                    Lecturer
    ## 2931                      SCHWARZE,GRETCHEN         Associate Professor
    ## 2932                      SCHWARZE,MICHELLE         Assistant Professor
    ## 2933                        SCHWEBACH,MOLLY                    Lecturer
    ## 2934                        SCHWEBER,HOWARD                   Professor
    ## 2935                      SCHWEBER,SIMONE A                   Professor
    ## 2936                     SCHWENDINGER,LAURA                   Professor
    ## 2937                         SCHWOCH,ROBERT                    Lecturer
    ## 2938                   SCOTT,JESSICA ALYSIA       Assoc Professor (Chs)
    ## 2939                SEABORG,ANDREW THOMPSON          Adjunct Instructor
    ## 2940                         SEEGER,ANDREAS                   Professor
    ## 2941                          SEELY,WILLIAM             Senior Lecturer
    ## 2942                      SEFFROOD,BENJAMIN           Adjunct Professor
    ## 2943                           SEIBEL,KATIE                    Lecturer
    ## 2944                   SEIBERT,CHRISTINE S.             Professor (Chs)
    ## 2945                   SEIDEL,COURTNEY LANE         Clinical Assoc Prof
    ## 2946                      SEIDENBERG,MARK S                   Professor
    ## 2947                         SEIDMAN,GAY W.                   Professor
    ## 2948                         SEIFTER,MIRIAM         Associate Professor
    ## 2949                   SEILER SCHULTZ,TRACY          Clinical Asst Prof
    ## 2950                       SELL,KATHERINE A           Faculty Associate
    ## 2951                           SEMANIK,MIKE        Asst Professor (Chs)
    ## 2952            SEMRAD-DOOLITTLE,PAMELA SUE       Dis Faculty Associate
    ## 2953                      SENCHYNE,JONATHAN         Associate Professor
    ## 2954                    SENECAL,PETER KELLY           Adjunct Asst Prof
    ## 2955                       SENES,ALESSANDRO                   Professor
    ## 2956                         SEO,SANG BYUNG         Assistant Professor
    ## 2957                       SEPPALAINEN,TIMO                   Professor
    ## 2958                             SERAG,SARA                    Lecturer
    ## 2959                        SESHADRI,ANANTH                   Professor
    ## 2960                            SESIL,JAMES             Senior Lecturer
    ## 2961                             SESTO,MARY         Associate Professor
    ## 2962                 SETALURI,VIJAYASARADHI                   Professor
    ## 2963                          SETHARES,BILL                   Professor
    ## 2964                           SETHI,AJAY K         Associate Professor
    ## 2965                        SEVERSON,ERIC L         Assistant Professor
    ## 2966                               SEXE,LIZ                    Lecturer
    ## 2967                      SEYS,TRISHA MARIE          Clinical Asst Prof
    ## 2968                     SHAFER-LANDAU,RUSS                   Professor
    ## 2969               SHAFFER,DAVID WILLIAMSON                   Professor
    ## 2970                            SHAH,DHAVAN                   Professor
    ## 2971                            SHAH,HEMANT                   Professor
    ## 2972                            SHAH,MANISH                   Professor
    ## 2973                          SHALABY,MARWA         Assistant Professor
    ## 2974                     SHALIASTOVICH,IVAN         Associate Professor
    ## 2975                         SHANKAR,ANANTH         Assistant Professor
    ## 2976                  SHANMUGANAYAGAM,DHANU         Assistant Professor
    ## 2977                       SHANNON,BENJAMIN              Assoc Lecturer
    ## 2978                               SHAO,JUN                   Professor
    ## 2979                          SHAPIRO,DEBRA       Dis Faculty Associate
    ## 2980                          SHAPIRO,LARRY                   Professor
    ## 2981                        SHAPIRO,MIKE A.          Asst Faculty Assoc
    ## 2982                          SHAPIRO,VADIM                   Professor
    ## 2983                          SHARAFI,MITRA                   Professor
    ## 2984                            SHARMA,DIYA       Honorary Assoc/Fellow
    ## 2985                        SHARMA,PRASHANT         Assistant Professor
    ## 2986                        SHARP,NATHANIEL         Assistant Professor
    ## 2987                      SHASHKO,ALEXANDER                    Lecturer
    ## 2988                      SHAW,BRET RANDALL         Associate Professor
    ## 2989                    SHAW,GILLIAN CURTIS         Clinical Instructor
    ## 2990                             SHAW,KELLY         Clinical Instructor
    ## 2991                     SHCHERBYNA,TATIANA         Assistant Professor
    ## 2992                         SHEAR,LESLIE D          Clinical Professor
    ## 2993                     SHEEDY,MELISSA ANN                    Lecturer
    ## 2994                     SHEEHAN JR.,JOHN P                   Professor
    ## 2995                           SHEEHAN,NORA         Clinical Instructor
    ## 2996                  SHEETS,MICHAEL DENNIS                   Professor
    ## 2997                         SHEIBANI,NADER                   Professor
    ## 2998                        SHELEF,MIRIAM A         Associate Professor
    ## 2999                           SHELEF,NADAV                   Professor
    ## 3000                 SHELTON-MORRIS,YOLANDA              Assoc Lecturer
    ## 3001                               SHEN,HAO         Assistant Professor
    ## 3002                          SHENKER,YORAM       Honorary Assoc/Fellow
    ## 3003                         SHENOI,HEMANTH           Adjunct Professor
    ## 3004                         SHEREOS,JENINE              Assoc Lecturer
    ## 3005                          SHERER,NATHAN         Associate Professor
    ## 3006                       SHERRARD,CHERENE                   Professor
    ## 3007                       SHEVELENKO,IRINA                   Professor
    ## 3008                           SHI,GUANMING                   Professor
    ## 3009                             SHI,LEYUAN                   Professor
    ## 3010                               SHI,PENG         Associate Professor
    ## 3011                            SHI,XIAOXIA                   Professor
    ## 3012                       SHIELDS,MORGAN R           Faculty Associate
    ## 3013                        SHIELDS,REBECCA                    Lecturer
    ## 3014                             SHIN,JIHAE         Assistant Professor
    ## 3015                          SHIN,JUNG-HYE         Associate Professor
    ## 3016                         SHINNERS,KEVIN                   Professor
    ## 3017                     SHISHEGAR,NASTARAN         Assistant Professor
    ## 3018                              SHIU,GARY                   Professor
    ## 3019                    SHIYANBOLA,OLAYINKA         Associate Professor
    ## 3020                         SHOEMAKER,KARL                   Professor
    ## 3021                         SHOHET,J. LEON                   Professor
    ## 3022                     SHORT,SARAH JESSIE         Assistant Professor
    ## 3023                          SHREVE,PORTER                   Professor
    ## 3024                         SHUBERT,AMANDA              Assoc Lecturer
    ## 3025                            SHULL,JAMES                   Professor
    ## 3026                      SHUMOW,JOSEPH DEY                    Lecturer
    ## 3027                            SHUSTA,ERIC                   Professor
    ## 3028                           SHUTSKE,JOHN                   Professor
    ## 3029                         SHUTTS,KRISTIN                   Professor
    ## 3030                        SIBERT,EDWIN L.                   Professor
    ## 3031                             SIDEL,MARK                   Professor
    ## 3032                           SIDELLE,ALAN                   Professor
    ## 3033                           SIEMSEN,ENNO                   Professor
    ## 3034                      SIFAKIS,EFTYCHIOS         Associate Professor
    ## 3035                    SIGLER,PATRICIA ANN         Assoc Faculty Assoc
    ## 3036                          SILBER,HANNAH                    Lecturer
    ## 3037                      SILBERNAGEL,JANET                   Professor
    ## 3038                            SILET,KARIN                    Lecturer
    ## 3039                             SILVA,ERIN         Associate Professor
    ## 3040                        SIMCOX,JUDITH A         Assistant Professor
    ## 3041                        SIMMONS,ERICA S         Associate Professor
    ## 3042                          SIMON,PHILIPP                   Professor
    ## 3043                           SIMPSON,GAIL                   Professor
    ## 3044                             SIMS,REVEL         Assistant Professor
    ## 3045                          SINCLAIR,MATT         Assistant Professor
    ## 3046                        SINCOULAR,RANDY              Assoc Lecturer
    ## 3047                     SINDELAR,JEFFREY J                   Professor
    ## 3048                             SINGER,BEN         Associate Professor
    ## 3049                      SINGER,BRADLEY S.                   Professor
    ## 3050                           SINGH,ANNE M         Associate Professor
    ## 3051                            SINGH,VIKAS                   Professor
    ## 3052                           SINHA,RAUNAK         Assistant Professor
    ## 3053                          SKALA,MELISSA                   Professor
    ## 3054                        SKARZYNSKI,BART         Assoc Faculty Assoc
    ## 3055                           SKOG,MARLENE         Assistant Professor
    ## 3056                              SKOP,AHNA                   Professor
    ## 3057                 SKRENTNY,JAMES DOUGLAS           Faculty Associate
    ## 3058                          SLACK,KRISTEN                   Professor
    ## 3059                            SLADKY,KURT          Clinical Professor
    ## 3060                         SLUKVIN,IGOR I                   Professor
    ## 3061                         SMEDEMA,ADAM R                    Lecturer
    ## 3062                   SMEDEMA,SUSAN MILLER                   Professor
    ## 3063               SMEEDING,TIMOTHY MICHAEL                   Professor
    ## 3064                       SMITH III,LESLIE         Associate Professor
    ## 3065                         SMITH,AMANDA G          Asst Faculty Assoc
    ## 3066                     SMITH,AMANDA MARIE                    Lecturer
    ## 3067                             SMITH,ANNE         Clinical Assoc Prof
    ## 3068                 SMITH,CATHERINE ARNOTT                   Professor
    ## 3069                      SMITH,CHRISTINE E         Clinical Instructor
    ## 3070                            SMITH,DAMON         Associate Professor
    ## 3071                             SMITH,DOUG                    Lecturer
    ## 3072                            SMITH,ELLEN         Clinical Assoc Prof
    ## 3073                     SMITH,HEATHER DAWN          Asst Faculty Assoc
    ## 3074              SMITH,JEANNINA ANTOINETTE       Assoc Professor (Chs)
    ## 3075                             SMITH,JEFF                   Professor
    ## 3076                        SMITH,JEFFREY A                   Professor
    ## 3077                    SMITH,JENNIFER ROSE         Assistant Professor
    ## 3078                         SMITH,JUDITH A         Associate Professor
    ## 3079                        SMITH,LESLEY J.          Clinical Professor
    ## 3080                        SMITH,LESLIE M.                   Professor
    ## 3081                          SMITH,LLOYD M                   Professor
    ## 3082                            SMITH,LONES                   Professor
    ## 3083                         SMITH,MARGARET                    Lecturer
    ## 3084                     SMITH,MICHELE ANNE         Clinical Instructor
    ## 3085                         SMITH,NICHOLAS         Assoc Outreach Spec
    ## 3086                            SMITH,SCOTT          Visiting Asst Prof
    ## 3087                  SMITH,TESSA KATHERINE         Clinical Instructor
    ## 3088                          SNEDDEN,TRACI         Assistant Professor
    ## 3089                     SNELL,JEFFREY TODD           Faculty Associate
    ## 3090                    SNYDER,ASHLEY MARIE              Assoc Lecturer
    ## 3091                     SNYDER,CHRISTOPHER         Clinical Assoc Prof
    ## 3092                           SNYDER,KEVIN         Clinical Instructor
    ## 3093                          SNYDER,MAGGIE                    Lecturer
    ## 3094                     SNYDER,VIRGINIA L.       Assoc Professor (Chs)
    ## 3095                       SOBER,ELLIOTT R.                   Professor
    ## 3096            SOBIESKA,ALEKSANDRA CECYLIA          Visiting Asst Prof
    ## 3097                       SOELVSTEN,MIKKEL         Assistant Professor
    ## 3098                              SOHI,GURI                   Professor
    ## 3099                            SOLDAT,DOUG                   Professor
    ## 3100                          SOLHEIM,KAREN          Clinical Professor
    ## 3101                    SOLIS LEMUS,CLAUDIA         Assistant Professor
    ## 3102                 SOMERS,KATERINA IDETTE         Assistant Professor
    ## 3103                         SONDEL,PAUL M.                   Professor
    ## 3104                            SONE,HIROKI         Assistant Professor
    ## 3105                            SONE,JUDITH                    Lecturer
    ## 3106                        SORENSEN,ALAN T                   Professor
    ## 3107                SORKNESS,CHRISTINE ANNE         Dis Professor (Chs)
    ## 3108                         SOSKOVA,MARIYA         Associate Professor
    ## 3109                           SOUKUP,JASON         Clinical Assoc Prof
    ## 3110                SOUNNY-SLITINE,M. ANWAR         Assoc Faculty Assoc
    ## 3111                        SOUTHGATE,HENRY                    Lecturer
    ## 3112                           SOVINEC,CARL                   Professor
    ## 3113                      SPAGNOLIE,SAVERIO         Associate Professor
    ## 3114                         SPALDING,EDGAR                   Professor
    ## 3115                       SPAULDING,DANIEL         Assistant Professor
    ## 3116                         SPEECE,BEVERLY           Faculty Associate
    ## 3117                        SPEIDEL,MICHAEL         Associate Professor
    ## 3118                        SPERLING,CARRIE          Clinical Professor
    ## 3119                  SPIKE,BENJAMIN THOMAS         Assoc Faculty Assoc
    ## 3120                      SPURGERS,RACHEL L                    Lecturer
    ## 3121                            SRACIC,MIKE         Assoc Faculty Assoc
    ## 3122                      SRAMEK,BARBARA JO          Clinical Professor
    ## 3123                        SRIDHARAN,KUMAR                   Professor
    ## 3124                         SRIDHARAN,RUPA         Associate Professor
    ## 3125                   ST JAMES,MARIKO LUCY         Clinical Instructor
    ## 3126                   STAFFORD,CATHERINE A         Associate Professor
    ## 3127                       STAHL,SHANNON S.                   Professor
    ## 3128                 STAJKOVIC,ALEXANDER D.         Associate Professor
    ## 3129                      STALEY,ROBIN ANNE                    Lecturer
    ## 3130                           STAMBACH,AMY                   Professor
    ## 3131                            STAMM,JULIE          Clinical Asst Prof
    ## 3132                    STANIC-KOSTIC,ALEKS         Assistant Professor
    ## 3133                   STANIMIROVIC,SNEZANA                   Professor
    ## 3134                         STANLEY,DONALD           Faculty Associate
    ## 3135                          STANLEY,EMILY                   Professor
    ## 3136                      STANTON,MEGAN ANN                    Lecturer
    ## 3137                        STATKIEWICZ,MAX         Associate Professor
    ## 3138                      STATMAN,ALEXANDER              Assoc Lecturer
    ## 3139                           STAUFFER,JIM         Assoc Faculty Assoc
    ## 3140                          STECHMANN,SAM                   Professor
    ## 3141                          STEEGE,LINSEY         Associate Professor
    ## 3142                          STEFFAN,SHAWN         Associate Professor
    ## 3143                        STEINBERG,JESSE           Faculty Associate
    ## 3144                       STEINER,JAMES D.             Senior Lecturer
    ## 3145                     STEINKAMP,LISA ANN        Asst Professor (Chs)
    ## 3146                     STEPHENSON,JASON W       Assoc Professor (Chs)
    ## 3147                        STEPIEN,REBECCA          Clinical Professor
    ## 3148               STERLING VON GLAHN,AUDRA         Associate Professor
    ## 3149                             STERN,ADAM         Assistant Professor
    ## 3150                         STERN,WALTER C         Assistant Professor
    ## 3151                          STEUDEL,HARRY              Professor Emer
    ## 3152                 STEVENS,ANDREW WILLIAM         Assistant Professor
    ## 3153                         STEVENSON,ADAM          Clinical Professor
    ## 3154                       STEWART,COLLETTE           Faculty Associate
    ## 3155                         STEWART,KATE L                    Lecturer
    ## 3156                    STEWART,KATHARINA S             Professor (Chs)
    ## 3157                          STIEGERT,KYLE                   Professor
    ## 3158                   STIETZ,KIMBERLY KEIL         Assistant Professor
    ## 3159                           STILL,THOMAS             Senior Lecturer
    ## 3160                          STITES,ALISON              Assoc Lecturer
    ## 3161                   STODDARD,JEREMY DOUD                   Professor
    ## 3162                      STOECKER,RANDY R.                   Professor
    ## 3163                          STOLL,LINDY K                    Lecturer
    ## 3164                      STOLTENBERG,DAVID                   Professor
    ## 3165                         STOLZ,DANIEL A         Assistant Professor
    ## 3166                        STONE,DONALD S.                   Professor
    ## 3167                 STONEHOUSE,FREDERICK A                   Professor
    ## 3168                            STORY,KAYLA                    Lecturer
    ## 3169                          STOVALL,BETSY         Associate Professor
    ## 3170                             STOWE,JOHN                   Professor
    ## 3171                             STOWE,RYAN         Assistant Professor
    ## 3172                        STOWE,ZACHARY N                   Professor
    ## 3173                            STOY,PAUL C         Associate Professor
    ## 3174                        STOYCHUK,OKSANA              Assoc Lecturer
    ## 3175                            STRAMPP,PIA              Assoc Lecturer
    ## 3176                    STRANG,KEVIN THOMAS       Dis Faculty Associate
    ## 3177                           STRAUS,SCOTT                   Professor
    ## 3178                    STREET,BRIAN THOMAS                   Professor
    ## 3179                          STREIFFER,ROB                   Professor
    ## 3180                         STRIER,KAREN B                   Professor
    ## 3181                         STRIKER,ROBERT         Associate Professor
    ## 3182               STROHL,NICHOLAS MCINTOSH                    Lecturer
    ## 3183                        STROJNY,SHELLEY           Faculty Associate
    ## 3184                           STRONG,LAURA           Adjunct Professor
    ## 3185                        STRZELEC,ANDREA          Asst Faculty Assoc
    ## 3186                   STUDER,LYNETTE MARIE          Clinical Asst Prof
    ## 3187                      SU,RUTHIE REBECCA        Asst Professor (Chs)
    ## 3188                     SUAREZ,SASHA MARIA         Assistant Professor
    ## 3189                SUAREZ-GONZALEZ,DARILIS          Asst Faculty Assoc
    ## 3190                            SUEN,GARRET         Associate Professor
    ## 3191                         SUGDEN,WILLIAM                   Professor
    ## 3192                       SUKIENNIK,JUSTIN         Assoc Faculty Assoc
    ## 3193              SULLIVAN,CHRISTOPHER JOHN         Assistant Professor
    ## 3194                         SUMINSKI,AARON         Assoc Faculty Assoc
    ## 3195                            SUNDE,ROGER                   Professor
    ## 3196                    SUNDLING,KAITLIN E.        Asst Professor (Chs)
    ## 3197                       SURASIN,JANPANIT             Senior Lecturer
    ## 3198                      SURDYK,JOHN SCOTT           Faculty Associate
    ## 3199                        SURESH,KRISHNAN                   Professor
    ## 3200                            SURI,DEVIKA          Asst Faculty Assoc
    ## 3201                          SUROVI,LAUREN                    Lecturer
    ## 3202                 SURYANARAYANAN,SAINATH              Assoc Lecturer
    ## 3203                     SUSSMAN,MICHAEL R.                   Professor
    ## 3204                    SUTULA,THOMAS PETER       Honorary Assoc/Fellow
    ## 3205                          SUZUKI,AUSSIE         Assistant Professor
    ## 3206                       SUZUKI,MASATOSHI         Associate Professor
    ## 3207                            SVAREN,JOHN                   Professor
    ## 3208                   SVENSON,JAMES ERNEST       Assoc Professor (Chs)
    ## 3209                           SWACK,JEANNE                   Professor
    ## 3210                           SWAN,HEATHER             Senior Lecturer
    ## 3211                            SWANEY,ROSS         Associate Professor
    ## 3212                           SWANKE,JAMES                    Lecturer
    ## 3213                         SWARTZ,ALEISHA         Clinical Instructor
    ## 3214              SWARTZENTRUBER,ELAINE KAY             Senior Lecturer
    ## 3215                      SWATKOWSKI,PAMELA           Adjunct Professor
    ## 3216                            SWEET,JAMES                   Professor
    ## 3217                          SWIFT,MICHAEL                   Professor
    ## 3218                        SYAMKUMAR,MEENA          Asst Faculty Assoc
    ## 3219                       SYDNOR,JUSTIN R.                   Professor
    ## 3220                          SYFOX,CHONTEL         Assistant Professor
    ## 3221                         SYTSMA,KENNETH                   Professor
    ## 3222                     SZLUFARSKA,IZABELA                   Professor
    ## 3223                            TABER,CHRIS                   Professor
    ## 3224                              TAHK,ALEX         Associate Professor
    ## 3225                          TAHK,SUSANNAH         Associate Professor
    ## 3226                              TAI,STEPH                   Professor
    ## 3227                         TAKADA,MARILIA         Clinical Instructor
    ## 3228                        TAKAHASHI,NAOMI          Asst Faculty Assoc
    ## 3229                    TALAAT,ADEL MOHAMED                   Professor
    ## 3230                         TALARCZYK,ALAN                Dis Lecturer
    ## 3231                     TAMPLIN,OWEN JAMES         Assistant Professor
    ## 3232                           TANG,WEIPING                   Professor
    ## 3233                        TANG,ZHENGZHENG         Assistant Professor
    ## 3234                     TANNENBAUM,MATTHEW              Assoc Lecturer
    ## 3235                           TANNER,ROBIN         Associate Professor
    ## 3236                   TANNU,SWAMIT SANDEEP         Assistant Professor
    ## 3237                TANSEY,TIMOTHY NICHOLAS                   Professor
    ## 3238                    TANUMIHARDJO,SHERRY                   Professor
    ## 3239                           TARVER,BECKY             Senior Lecturer
    ## 3240                              TAS,SINAN               Asst Prof L/I
    ## 3241                           TAYLOR,BRIAN              Assoc Lecturer
    ## 3242                     TAYLOR,CHRISTOPHER                   Professor
    ## 3243                        TAYLOR,HOWARD W          Adjunct Instructor
    ## 3244               TAYLOR,JOLANDA VANDERWAL                   Professor
    ## 3245                         TAYLOR,MATTHEW                    Lecturer
    ## 3246                         TAYLOR,MICHAEL         Assistant Professor
    ## 3247                 TAYLOR-MARSHALL,SANDRA                    Lecturer
    ## 3248                     TEBBE,ELLIOT AARON         Assistant Professor
    ## 3249                           TEEPLE,SCOTT                   Professor
    ## 3250                       TEIXEIRA,LEANDRO         Assistant Professor
    ## 3251                TEJEDO-HERRERO,FERNANDO         Associate Professor
    ## 3252                            TEMPLE,JACK         Clinical Instructor
    ## 3253                    TEMTE,JONATHAN LANE             Professor (Chs)
    ## 3254                     TEODORESCU,MIHAELA                   Professor
    ## 3255                    TERASAWA-GRILLEY,EI                   Professor
    ## 3256                            TERLAAK,ANN         Associate Professor
    ## 3257                          TERRY,PAUL W.                   Professor
    ## 3258                    TERWILLIGER,PAUL M.                   Professor
    ## 3259                     TESLAA,JESSICA JOY          Asst Faculty Assoc
    ## 3260                             THAL,SARAH                   Professor
    ## 3261                   THATCHER,GRAHAM PAUL          Clinical Asst Prof
    ## 3262                 THEBAULT-SPIEKER,JACOB         Assistant Professor
    ## 3263                             THEIN,JILL       Assoc Professor (Chs)
    ## 3264                    THEIS,MONICA LOUISE                Dis Lecturer
    ## 3265                           THEISEN,CARA          Asst Faculty Assoc
    ## 3266                          THELEN,DARRYL                   Professor
    ## 3267                   THEOBALD,ANNE LOUISE           Faculty Associate
    ## 3268                          THERTUS,KETTY          Clinical Asst Prof
    ## 3269                  THEVAMARAN,RAMATHASAN         Assistant Professor
    ## 3270                        THIBEAULT,SUSAN                   Professor
    ## 3271                          THIEL,ABIGAIL              Assoc Lecturer
    ## 3272                    THIFFEAULT,JEAN-LUC                   Professor
    ## 3273                         THIMMIG,LESLIE                   Professor
    ## 3274                              THOMA,DAN                   Professor
    ## 3275                         THOMA,SHARON L           Faculty Associate
    ## 3276                           THOMAS,ALVIN         Assistant Professor
    ## 3277                         THOMAS,MICHAEL                   Professor
    ## 3278                        THOMAS,TYLER F.         Assistant Professor
    ## 3279                             THOMAS,ZEB              Assoc Lecturer
    ## 3280                         THOMPSON,ANITA                   Professor
    ## 3281                         THOMPSON,CRAIG                   Professor
    ## 3282           THOMPSON,DAKOTAH RITTENHOUSE         Assistant Professor
    ## 3283                        THOMPSON,DEAN A                    Lecturer
    ## 3284                       THOMPSON,KATRINA                   Professor
    ## 3285                         THOMPSON,MINDI                   Professor
    ## 3286                        THOMPSON,RYAN J        Asst Professor (Chs)
    ## 3287                       THOMSON,JAMES A.                   Professor
    ## 3288                THORLEIFSDOTTIR,KRISTIN         Assistant Professor
    ## 3289                       THURBER,CLIFFORD                   Professor
    ## 3290                           THURBER,MARY         Clinical Instructor
    ## 3291                          THURLOW,JULIE           Faculty Associate
    ## 3292                   THURS,DANIEL PATRICK          Asst Faculty Assoc
    ## 3293                   TIBBETTS,RANDAL SCOT                   Professor
    ## 3294                    TIBORIS,MICHAEL GUS             Senior Lecturer
    ## 3295                       TIDWELL,TAWNI L.              Assoc Lecturer
    ## 3296                           TIKOFF,BASIL                   Professor
    ## 3297                       TILLER,HEATHER S         Assoc Faculty Assoc
    ## 3298                    TILMANN,CHRISTOPHER           Faculty Associate
    ## 3299                        TIMBIE,PETER T.                   Professor
    ## 3300                           TIMLER,TESSA              Assoc Lecturer
    ## 3301                    TIMM,DANIEL JEFFREY           Faculty Associate
    ## 3302                            TIMM,STEVEN           Faculty Associate
    ## 3303                          TINGLUM,TRINA                    Lecturer
    ## 3304                           TINJUM,JAMES         Associate Professor
    ## 3305                TISCHAUSER,JEFF GARNETT                    Lecturer
    ## 3306                  TISHLER,JENNIFER RYAN           Faculty Associate
    ## 3307                      TITELBAUM,MICHAEL                   Professor
    ## 3308                      TJOSTHEIM,SONJA S          Clinical Asst Prof
    ## 3309                          TOBIN,MICHAEL          Adjunct Instructor
    ## 3310                      TOCHON,FRANCOIS V                   Professor
    ## 3311                       TODOROVIC,JELENA         Associate Professor
    ## 3312                       TOLLIVER,SARA E.         Clinical Instructor
    ## 3313                TOLSON,YOLANDA MICHELLE          Clinical Professor
    ## 3314                          TOMA,CATALINA         Associate Professor
    ## 3315                         TOMLINSON,KATY       Student Services Cord
    ## 3316                     TOMPKINS,WILLIS J.              Professor Emer
    ## 3317                            TONG,JORDAN         Associate Professor
    ## 3318                          TONGDAENG,EVE                    Lecturer
    ## 3319                          TONONI,GIULIO                   Professor
    ## 3320                         TOWNSEND,EMILY              Assoc Lecturer
    ## 3321                        TOWNSEND,PHILIP                   Professor
    ## 3322                     TOWNSEND,RICHARD H                   Professor
    ## 3323                          TRACY,WILLIAM                   Professor
    ## 3324                         TRAN,HUNG VINH         Associate Professor
    ## 3325                     TRAVERS,BRITTANY G         Associate Professor
    ## 3326                TRAYNOR,SARAH ELIZABETH              Assoc Lecturer
    ## 3327                              TREJO,SAM         Assistant Professor
    ## 3328                       TREMONTI,CHRISTY         Associate Professor
    ## 3329                       TREPANIER,LAUREN                   Professor
    ## 3330                            TREST,MARIE         Assoc Faculty Assoc
    ## 3331                          TREVES,ADRIAN                   Professor
    ## 3332                  TREVINO-MURPHY,ALICIA              Assoc Lecturer
    ## 3333                         TREVOR,CHARLIE                   Professor
    ## 3334                    TREZEK,BEVERLY JANE         Associate Professor
    ## 3335                           TRIANA,MARIA         Associate Professor
    ## 3336                     TRIGSTED,STEPHANIE          Asst Faculty Assoc
    ## 3337                    TRIMBELL,KOHL MARIE                    Lecturer
    ## 3338                     TRIPOLI,GREGORY J.                   Professor
    ## 3339                             TRIPP,AILI                   Professor
    ## 3340                           TROTTER,MARY         Associate Professor
    ## 3341                         TROWBRIDGE,AMY         Assistant Professor
    ## 3342                     TRUE,JAMES MICHAEL          Adjunct Instructor
    ## 3343                         TRUJILLO,MARIO         Associate Professor
    ## 3344                        TRYON,ELIZABETH            Sr Outreach Spec
    ## 3345                        TUCKER,PATRICIA                    Lecturer
    ## 3346                   TUERKHEIMER,FRANK M.              Professor Emer
    ## 3347                            TULI,SACHIN           Faculty Associate
    ## 3348                          TUMARKIN,ANNA           Faculty Associate
    ## 3349                       TUN,SAN SAN HNIN           Faculty Associate
    ## 3350                         TUREK,MICHELLE         Clinical Assoc Prof
    ## 3351                          TURNER,ANDREW                    Lecturer
    ## 3352                    TURNER,ANDREW JASON                    Lecturer
    ## 3353                           TURNER,ERICA         Associate Professor
    ## 3354                      TURNER,KRISTOPHER              Assoc Lecturer
    ## 3355                         TURNER,MATTHEW                   Professor
    ## 3356                       TURNER,MONICA G.                   Professor
    ## 3357                        TURNG,LIH-SHENG                   Professor
    ## 3358                         TYLER,MITCHELL       Honorary Assoc/Fellow
    ## 3359                        TZAMOS,CHRISTOS         Assistant Professor
    ## 3360                    UDVARI-SOLNER,ALICE           Faculty Associate
    ## 3361                            UHLRICH,DAN                   Professor
    ## 3362                      ULLAND,TYLER KENT         Assistant Professor
    ## 3363                        UNDERWOOD,JULIE                   Professor
    ## 3364                     UPAH,BARTHOLOMEW G                    Lecturer
    ## 3365                    URNESS,CHARLES TODD                    Lecturer
    ## 3366                         URRUTIA,MATTIE           Faculty Associate
    ## 3367                         USECHE,ALLISON         Assistant Professor
    ## 3368                       USSISHKIN,DANIEL         Associate Professor
    ## 3369                            VAID,UCHITA         Assistant Professor
    ## 3370                             VAIL,DAVID                   Professor
    ## 3371               VALENCIA,SARAH ELIZABETH              Assoc Lecturer
    ## 3372                       VALEO COOKE,NINA           Faculty Associate
    ## 3373                          VALKO,BENEDEK                   Professor
    ## 3374                         VALLEY,JOHN W.                   Professor
    ## 3375                            VALLON,MARC                   Professor
    ## 3376                   VAN  HALLGREN,CARRIE             Senior Lecturer
    ## 3377                VAN ASSELT,NATHANIEL C.          Clinical Asst Prof
    ## 3378                  VAN DAN,REBECCA SUSAN              Assoc Lecturer
    ## 3379                     VAN DE WATER,MANON                   Professor
    ## 3380                     VAN DEELEN,TIMOTHY                   Professor
    ## 3381                   VAN DER WEIDE,DANIEL                   Professor
    ## 3382              VAN DYKE JR.,KENNETH JOHN       Assoc Professor (Chs)
    ## 3383                      VAN KAN,PETER L E         Associate Professor
    ## 3384                        VAN LEHN,REID C         Assistant Professor
    ## 3385                   VAN MALE,THERESE ANN           Faculty Associate
    ## 3386                   VAN MELKEBEEK,DIETER                   Professor
    ## 3387                        VAN OS,JENNIFER         Assistant Professor
    ## 3388                 VAN PIJKEREN,JAN PETER         Associate Professor
    ## 3389                        VAN RIJN,JORDAN                    Lecturer
    ## 3390               VAN RYBROEK,GREGORY JOHN           Adjunct Asst Prof
    ## 3391               VAN SICKLEN,BARRET VILAS          Adjunct Instructor
    ## 3392                           VAN SWOL,LYN                   Professor
    ## 3393                      VANCAMP,ELIJAH B.          Adjunct Instructor
    ## 3394                     VANDEN HEUVEL,MIKE                   Professor
    ## 3395                   VANDENBROUCKE,JUSTIN         Associate Professor
    ## 3396                     VANDER ZANDEN,JAKE                   Professor
    ## 3397                      VANDERBURG,ANDREW         Assistant Professor
    ## 3398                 VANDERWALL,CASSANDRA M           Adjunct Asst Prof
    ## 3399                          VANVEEN,BARRY                   Professor
    ## 3400                              VARDI,URI                   Professor
    ## 3401                          VARESCHI,MARK         Associate Professor
    ## 3402                       VARGAS,MARCELO R         Assistant Professor
    ## 3403                VARGAS-PRIETO,ALBERTO M           Faculty Associate
    ## 3404                          VARGHESE,TOMY                   Professor
    ## 3405                           VARSAVA,NINA         Assistant Professor
    ## 3406                         VATAN,FLORENCE                   Professor
    ## 3407                   VAUGHAN,BRIAN DWIGHT                    Lecturer
    ## 3408                        VAVILOV,MAXIM G                   Professor
    ## 3409                          VEERAMANI,RAJ                   Professor
    ## 3410                            VEITH,TONYA          Clinical Asst Prof
    ## 3411              VELLIQUETTE,MICHAEL JAMES           Faculty Associate
    ## 3412                     VELTEN,ANDREAS UDO         Assistant Professor
    ## 3413                        VEMUGANTI,RAGHU                   Professor
    ## 3414                  VENKATARAMAN,SHIVARAM         Assistant Professor
    ## 3415                    VENKATARAMANAN,GIRI                   Professor
    ## 3416                          VENTURA,STEVE                   Professor
    ## 3417                     VENTURELLI,OPHELIA         Assistant Professor
    ## 3418                     VENTURINI,MICHELLE           Adjunct Professor
    ## 3419                        VERBRUGGE,MARIA         Clinical Instructor
    ## 3420                   VERMILLION,KATIE LEE         Assoc Faculty Assoc
    ## 3421                     VESTLING,MARTHA M.            Senior Scientist
    ## 3422                         VEZINA,CHAD M.                   Professor
    ## 3423                         VICKROY,CHERYL           Adjunct Professor
    ## 3424                       VIEIRA,CATHERINE                   Professor
    ## 3425                              VILA,ANNE                   Professor
    ## 3426                       VILLAGRAN,JOSE G              Assoc Lecturer
    ## 3427                          VIMONT,DANIEL                   Professor
    ## 3428                         VINEY,GRETCHEN           Dis Clinical Prof
    ## 3429                     VITCENDA,ANGELA K.          Clinical Asst Prof
    ## 3430                             VIVIAN,EVA             Professor (Chs)
    ## 3431                   VIVIANO,KATRINA ROSE         Clinical Assoc Prof
    ## 3432                            VLACH,HALEY         Associate Professor
    ## 3433                            VOGE,CASSIE         Clinical Assoc Prof
    ## 3434                        VOILS,CORRINE I                   Professor
    ## 3435                     VON SIMSON,CHARLES         Clinical Assoc Prof
    ## 3436                      VOPAL,EDWARD JOHN          Adjunct Instructor
    ## 3437                            VOYLES,PAUL                   Professor
    ## 3438                     VRANAS,PETER B. M.                   Professor
    ## 3439                            VUE,GOODSON                    Lecturer
    ## 3440                      WACKER,LEEANN SOO               Professor L/I
    ## 3441                          WAGGONER,JESS         Assistant Professor
    ## 3442                           WAGH,SIDDESH          Visiting Asst Prof
    ## 3443                         WAGNER,AMY LEE                    Lecturer
    ## 3444                            WAGNER,BRIT              Assoc Lecturer
    ## 3445                         WAGNER,MICHAEL                   Professor
    ## 3446                            WAGNER,MIKE         Assistant Professor
    ## 3447                             WAGNER,ROB         Assoc Faculty Assoc
    ## 3448                      WAGNER,TERA HOLTZ           Faculty Associate
    ## 3449                           WAGNER,TIAHA         Clinical Instructor
    ## 3450                       WAGNER,TIMOTHY J                    Lecturer
    ## 3451                            WAHEED,SANA        Asst Professor (Chs)
    ## 3452                        WAKAI,RONALD T.                   Professor
    ## 3453                        WAKKER,BASTIAAN              Assoc Lecturer
    ## 3454                           WALASZEK,ART             Professor (Chs)
    ## 3455             WALBRANDT PIGARELLI,DENISE       Assoc Professor (Chs)
    ## 3456               WALDEN,JUSTINE ANGELIQUE                    Lecturer
    ## 3457                           WALDRON,ALEX         Assistant Professor
    ## 3458                         WALEFFE,FABIAN                   Professor
    ## 3459                   WALKER,CHRISTOPHER A                   Professor
    ## 3460                         WALKER,JAMES R                   Professor
    ## 3461                         WALKER,JULIE M         Clinical Assoc Prof
    ## 3462                          WALKER,THAD G                   Professor
    ## 3463                    WALLACE,GEOFFREY L.         Associate Professor
    ## 3464                   WALLACE,SUZANNE BETH          Clinical Asst Prof
    ## 3465                             WALLER,KEN         Clinical Assoc Prof
    ## 3466                          WALLER,SHELLY                    Lecturer
    ## 3467                      WALLMANN,JOHANNES         Associate Professor
    ## 3468                         WALSH,JENNIFER                    Lecturer
    ## 3469                      WALSH,JOHN EDWARD             Senior Lecturer
    ## 3470                         WALSH,JOSEPH G           Faculty Associate
    ## 3471                             WALSH,KATE         Associate Professor
    ## 3472               WALSH,MATTHEW CUNNINGHAM                    Lecturer
    ## 3473                           WALSH,TOVA B         Assistant Professor
    ## 3474                       WALTER,ALEXANDRA                    Lecturer
    ## 3475                      WANDEL,LEE PALMER                   Professor
    ## 3476                            WANG,BOTONG         Assistant Professor
    ## 3477                                WANG,BU         Assistant Professor
    ## 3478                           WANG,DAIFENG         Assistant Professor
    ## 3479                               WANG,HAN         Assistant Professor
    ## 3480              WANG,JENNIFER LYNN HYLAND                    Lecturer
    ## 3481                               WANG,JUE                   Professor
    ## 3482                              WANG,MARY           Faculty Associate
    ## 3483                           WANG,MIAOYAN         Assistant Professor
    ## 3484                              WANG,TINA         Assistant Professor
    ## 3485                               WANG,XIN         Assistant Professor
    ## 3486                            WANG,XUDONG                   Professor
    ## 3487                             WANG,XUELI                   Professor
    ## 3488                              WANG,YANG         Associate Professor
    ## 3489                            WANG,YAZHEN                   Professor
    ## 3490                                WANG,YI         Assistant Professor
    ## 3491                              WANG,YING         Assistant Professor
    ## 3492                       WANGERIN, JOANNA             Senior Lecturer
    ## 3493                           WANGERIN,DAN         Associate Professor
    ## 3494                            WANNER,ANJA                   Professor
    ## 3495                       WARD,DAVID ALLEN             Senior Lecturer
    ## 3496                           WARD,EARLISE                   Professor
    ## 3497                           WARD,EMILY J         Assistant Professor
    ## 3498                   WARDRIP,PETER THOMAS         Assistant Professor
    ## 3499                       WARFIELD,TERRY D                   Professor
    ## 3500                WARGOWSKI,DAVID STEPHAN             Professor (Chs)
    ## 3501                       WARNER,H WILLIAM              Assoc Lecturer
    ## 3502                WARREN ANDERSEN,SHANEDA         Assistant Professor
    ## 3503                        WASSARMAN,DAVID                   Professor
    ## 3504                        WASSARMAN,KAREN                   Professor
    ## 3505                          WATSON,ANDREW         Assistant Professor
    ## 3506                          WATTERS,JYOTI                   Professor
    ## 3507                        WATTIAUX,MICHEL                   Professor
    ## 3508                           WATTS,STEVEN                    Lecturer
    ## 3509                      WAX,AUDREY LAUREN                    Lecturer
    ## 3510                          WEAVER,BETH A         Associate Professor
    ## 3511                          WEAVER,JEREMY           Faculty Associate
    ## 3512                            WEBER,JESSE         Assistant Professor
    ## 3513                            WEBERT,KYLE          Asst Faculty Assoc
    ## 3514                              WEEKS,AMY         Assistant Professor
    ## 3515                          WEEKS,JESSICA                   Professor
    ## 3516                             WEI,HAORAN         Assistant Professor
    ## 3517                      WEICHERT,JAMEY P.                   Professor
    ## 3518                            WEIGEL,KENT                   Professor
    ## 3519                         WEIGOLD,URSULA          Clinical Professor
    ## 3520                            WEIMER,DAVE                   Professor
    ## 3521                             WEISS,LIAD         Assistant Professor
    ## 3522                     WEISSHAAR,JAMES C.                   Professor
    ## 3523                       WEIX,DANIEL JOHN                   Professor
    ## 3524                           WELCH,RODNEY                   Professor
    ## 3525                          WELHAM,NATHAN         Associate Professor
    ## 3526                    WELLIK,DENEEN MARIE                   Professor
    ## 3527                            WELLS,SARAH         Associate Professor
    ## 3528                   WELTON,ANJALE DEVAWN                   Professor
    ## 3529                        WEMMERLOV,URBAN                   Professor
    ## 3530                  WENDLAND,CLAIRE LEONE                   Professor
    ## 3531                              WENDT,AMY                   Professor
    ## 3532                        WENDT,MARK ALAN           Faculty Associate
    ## 3533                             WENG,YIQUN                   Professor
    ## 3534                             WENKER,SUE        Asst Professor (Chs)
    ## 3535                     WENTHUR,CODY JAMES         Assistant Professor
    ## 3536                          WERETKA,MAREK         Associate Professor
    ## 3537                          WERLE,RODRIGO         Assistant Professor
    ## 3538                          WERLING,DONNA         Assistant Professor
    ## 3539                           WERNER,CRAIG              Professor Emer
    ## 3540                          WERNER,NICOLE         Assistant Professor
    ## 3541                   WEST,CHARLES RAYMOND             Senior Lecturer
    ## 3542                           WEST,CYNTHIA                    Lecturer
    ## 3543                        WEST,KENNETH D.                   Professor
    ## 3544               WESTERGAARD,RYAN PATRICK         Associate Professor
    ## 3545                     WESTLER,WILLIAM M.               Dis Scientist
    ## 3546                     WESTMARK,CARA JEAN         Assistant Professor
    ## 3547                        WHEELER,DERIC L         Associate Professor
    ## 3548                       WHELAN,CHRISTINE         Assoc Faculty Assoc
    ## 3549                          WHITE,HEATHER         Associate Professor
    ## 3550                        WHITE,MONICA M.         Associate Professor
    ## 3551                            WHITE,SARAH         Clinical Instructor
    ## 3552                 WHITING,GLORIA MCCAHON         Assistant Professor
    ## 3553                           WHITMAN,THEA         Assistant Professor
    ## 3554                      WHITMIRE,ETHELENE                   Professor
    ## 3555                           WHITMORE,KIM         Assistant Professor
    ## 3556                          WHITTLE,BRUNO         Assistant Professor
    ## 3557                         WICKENS,ZACH K         Assistant Professor
    ## 3558                 WIDICUS WEAVER,SUSANNA                   Professor
    ## 3559                       WIDMAYER,CHRISSY                    Lecturer
    ## 3560                          WIEBEN,OLIVER                   Professor
    ## 3561                        WIEDENHOEFT,BOB                    Lecturer
    ## 3562                     WIEGMANN,DOUGLAS A         Associate Professor
    ## 3563                       WIEGMANN,SUSAN M         Assoc Faculty Assoc
    ## 3564                      WIENHOLTS,JOHANNA                    Lecturer
    ## 3565                      WIERCIOCH,GREGORY         Clinical Assoc Prof
    ## 3566                      WIESSINGER,NICOLE         Assoc Faculty Assoc
    ## 3567                           WILCOTS,ERIC                   Professor
    ## 3568                       WILD,PROF JOHN J                   Professor
    ## 3569                      WILDONGER,JILL C.         Associate Professor
    ## 3570                     WILES,BRADLEY JOHN              Assoc Lecturer
    ## 3571                     WILKERSON,KIMBER L                   Professor
    ## 3572                        WILKINSON,GRACE         Assistant Professor
    ## 3573                      WILKINSON,KRISTIN                    Lecturer
    ## 3574                          WILLE,CHRISTA              Assoc Lecturer
    ## 3575                           WILLES,MEGAN                    Lecturer
    ## 3576                        WILLETT,REBEKAH         Associate Professor
    ## 3577                        WILLIAMS,JACK W                   Professor
    ## 3578                     WILLIAMS,JAHMESE M          Asst Faculty Assoc
    ## 3579                           WILLIAMS,JIM         Assoc Faculty Assoc
    ## 3580                   WILLIAMS,JUSTIN COLE                   Professor
    ## 3581                        WILLIAMS,MAKEBA         Clinical Assoc Prof
    ## 3582                     WILLIAMS,MICHAEL L           Faculty Associate
    ## 3583                        WILLIAMS,NOAH M                   Professor
    ## 3584                      WILLIAMS,SCOTT P.          Asst Faculty Assoc
    ## 3585                       WILLIAMSON,BRADY       Honorary Assoc/Fellow
    ## 3586                    WILLIAMSON,LILLIE D         Assistant Professor
    ## 3587                       WILLIAMSON,SARAH           Faculty Associate
    ## 3588                       WILLIFORD,DANIEL         Assistant Professor
    ## 3589                         WILLITS,ANGELA         Clinical Assoc Prof
    ## 3590                          WILLMANN,KARL       Assoc Professor (Chs)
    ## 3591                         WILSON,BETHANY          Adjunct Instructor
    ## 3592                            WILSON,PAUL                   Professor
    ## 3593                          WILTBANK,MILO                   Professor
    ## 3594                  WINCENTSEN,HEIDI LYNN           Faculty Associate
    ## 3595                     WINDSOR,JAMES MARK                    Lecturer
    ## 3596               WINKLE-WAGNER,RACHELLE L                   Professor
    ## 3597                           WINSTON,TINA           Faculty Associate
    ## 3598             WINTERSTEIN,ANDREW PATRICK           Dis Clinical Prof
    ## 3599                  WISWALL,MATTHEW JAMES                   Professor
    ## 3600                   WITZENBURG,COLLEEN M         Assistant Professor
    ## 3601                      WIXON,DEVIN LAURA                    Lecturer
    ## 3602                          WIYAKA,DENISE           Faculty Associate
    ## 3603                       WODZYNSKI,LUKASZ         Assistant Professor
    ## 3604                           WOLF,KIRSTEN                   Professor
    ## 3605                          WOLF,MARSHA J            Senior Scientist
    ## 3606                  WOLINSKY,ZACHARY EVAN              Assoc Lecturer
    ## 3607                          WOLLACK,JAMES                   Professor
    ## 3608                  WOLLACK,JODI ERIKSSON                    Lecturer
    ## 3609                   WONG,NANCY YEE CHING                   Professor
    ## 3610                            WOOD, SARAH             Senior Lecturer
    ## 3611                   WOOD,MICHAEL WILLAIM          Clinical Asst Prof
    ## 3612                              WOODS,JON                   Professor
    ## 3613                    WOODS,ROBERT CLAUDE                   Professor
    ## 3614                   WOODWARD,CATHERINE L         Assoc Faculty Assoc
    ## 3615                         WOODWARD,KEITH                   Professor
    ## 3616                    WORZELLA,TRACY JEAN       Honorary Assoc/Fellow
    ## 3617                          WRIGHT,DANIEL         Assistant Professor
    ## 3618                     WRIGHT,ELIZABETH R                   Professor
    ## 3619                            WRIGHT,JOHN              Professor Emer
    ## 3620                         WRIGHT,RANDALL                   Professor
    ## 3621                       WRIGHT,STEPHEN J                   Professor
    ## 3622                   WRIGHT,STEVEN HOWARD         Clinical Assoc Prof
    ## 3623                          WRIGHT,TRAVIS         Associate Professor
    ## 3624                            WU,BI CHENG              Assoc Lecturer
    ## 3625                              WU,CHENXI         Assistant Professor
    ## 3626                              WU,CHIN H                   Professor
    ## 3627                             WU,DESMUND              Assoc Lecturer
    ## 3628                          WU,SAU LAN YU                   Professor
    ## 3629                          WYNE,KEVIN T.           Faculty Associate
    ## 3630                          XENOS,MICHAEL                   Professor
    ## 3631                            XING,YONGNA         Associate Professor
    ## 3632                         XIONG,YANG SAO         Assistant Professor
    ## 3633                             XU,HUIFANG                   Professor
    ## 3634                                XU,TINA                    Lecturer
    ## 3635                                 XU,WEI                   Professor
    ## 3636                             XU,XIANGRU         Assistant Professor
    ## 3637                          YABLON,ROBERT         Associate Professor
    ## 3638                           YACKEE,JASON                   Professor
    ## 3639                         YACKEE,SUSAN W                   Professor
    ## 3640                          YAHN,JEREMIAH           Faculty Associate
    ## 3641                          YANDELL,BRIAN                   Professor
    ## 3642                                YANG,BO          Asst Faculty Assoc
    ## 3643                             YANG,SIJIA         Assistant Professor
    ## 3644                           YANG,TONGHAI                   Professor
    ## 3645                              YANG,YANG         Assistant Professor
    ## 3646                     YAUCH,CHARLENE ANN         Assoc Faculty Assoc
    ## 3647                         YAVAS,ABDULLAH                   Professor
    ## 3648                            YAVUZ,DENIZ                   Professor
    ## 3649                               YEN,ERIC         Associate Professor
    ## 3650                         YESILKOY,FILIZ         Assistant Professor
    ## 3651                          YETHIRAJ,ARUN                   Professor
    ## 3652                     YIN,JERRY CHI-PING                   Professor
    ## 3653                               YIN,JOHN                   Professor
    ## 3654                            YIN,TOM C T       Honorary Assoc/Fellow
    ## 3655                           YOON,TEHSHIK                   Professor
    ## 3656                            YOOSE,BECKY              Assoc Lecturer
    ## 3657                              YOUNG,DAN                   Professor
    ## 3658                           YOUNG,LOUISE                   Professor
    ## 3659                 YOUNG,MORGAN ELISABETH          Adjunct Instructor
    ## 3660                           YOUNG,MORRIS                   Professor
    ## 3661                        YOUNG,RICHARD F                   Professor
    ## 3662                          YOUNG,STEPHEN         Associate Professor
    ## 3663                            YU,JAE-HYUK                   Professor
    ## 3664                             YU,JIN-WEN                   Professor
    ## 3665                                  YU,JP         Assistant Professor
    ## 3666                                YU,LIAN                   Professor
    ## 3667                            YU,MENGGANG                   Professor
    ## 3668                             YU,TIMOTHY                   Professor
    ## 3669                            YU,XIANGYAO         Assistant Professor
    ## 3670                              YU,ZONGFU         Associate Professor
    ## 3671                          YUDKOFF,SUNNY         Assistant Professor
    ## 3672                        ZACHARIA,NICOLE         Assoc Faculty Assoc
    ## 3673                         ZACHARSKI,GREG        Professor Of Mil Sci
    ## 3674                          ZAHASKY,CHRIS         Assistant Professor
    ## 3675                       ZAKOWSKI,LAURA J             Professor (Chs)
    ## 3676                            ZALAPA,JUAN         Associate Professor
    ## 3677                       ZAMANIAN,MOSTAFA         Assistant Professor
    ## 3678                           ZAMAR,SHEILA              Assoc Lecturer
    ## 3679                    ZANNI,MARTIN THOMAS                   Professor
    ## 3680                  ZAPATA,JASMINE YVONNE        Asst Professor (Chs)
    ## 3681                          ZARZAUR,BEN L                   Professor
    ## 3682                   ZAVALA-TEJEDA,VICTOR         Associate Professor
    ## 3683                    ZAYAS-CABAN,GABRIEL         Assistant Professor
    ## 3684                     ZDEBLICK,THOMAS A.                   Professor
    ## 3685                         ZEDLER,PAUL H.                   Professor
    ## 3686                          ZEHMS,KARLA M                   Professor
    ## 3687                   ZELENSKI,AMY BARBARA        Asst Professor (Chs)
    ## 3688                   ZELEWSKI,LINDA MARIE             Senior Lecturer
    ## 3689                  ZEPEDA-NUNEZ,LEONARDO         Assistant Professor
    ## 3690                         ZERVOU,NATALIE         Assistant Professor
    ## 3691                         ZHANG CHUNMING                   Professor
    ## 3692                          ZHANG XIAOFEI        Asst Professor (Chs)
    ## 3693                             ZHANG,ANRU         Assistant Professor
    ## 3694                            ZHANG,DAYIN         Assistant Professor
    ## 3695                         ZHANG,HONGMING                   Professor
    ## 3696                             ZHANG,JIAO                    Lecturer
    ## 3697                             ZHANG,JING                   Professor
    ## 3698                               ZHANG,KE         Assistant Professor
    ## 3699                           ZHANG,TIANLU          Asst Faculty Assoc
    ## 3700                     ZHANG,XIUJUAN JANE                    Lecturer
    ## 3701                            ZHANG,YIWEI         Assistant Professor
    ## 3702                         ZHANG,YONGFENG         Assistant Professor
    ## 3703                         ZHANG,ZHENGJUN                   Professor
    ## 3704                             ZHANG,ZHOU         Assistant Professor
    ## 3705                               ZHAO,FEI         Assistant Professor
    ## 3706                             ZHAO,JIWEI         Assistant Professor
    ## 3707                             ZHAO,XINYU                   Professor
    ## 3708                            ZHAO,YUHANG         Assistant Professor
    ## 3709                             ZHENG,JING                   Professor
    ## 3710                           ZHONG,XUEHUA         Associate Professor
    ## 3711                           ZHOU,JIAZHEN              Assoc Prof L/I
    ## 3712                             ZHOU,SHIYU                   Professor
    ## 3713                          ZHOU,YONGMING                   Professor
    ## 3714                             ZHU,A-XING                   Professor
    ## 3715                              ZHU,JERRY                   Professor
    ## 3716                                ZHU,JUN                   Professor
    ## 3717                             ZHU,WEIHUA         Associate Professor
    ## 3718                            ZHU,ZHENHUA         Assistant Professor
    ## 3719                         ZICKUHR,THOMAS                    Lecturer
    ## 3720                     ZILBERGERTS,MARINA         Assistant Professor
    ## 3721                          ZIMMER,ANDREW         Assistant Professor
    ## 3722                        ZIMMERMAN,DAVID                   Professor
    ## 3723                          ZINK,DANIELLE              Assoc Lecturer
    ## 3724                              ZINN,MIKE         Associate Professor
    ## 3725                         ZITZER,NINA C.          Clinical Asst Prof
    ## 3726                          ZOET,LUCAS K.         Assistant Professor
    ## 3727                 ZOROMSKI,LORRAINE MARY           Faculty Associate
    ## 3728                    ZUCKERBERG,BENJAMIN         Associate Professor
    ## 3729                 ZUEHLKE,AMANDA CELESTE         Assoc Faculty Assoc
    ## 3730                       ZUELSDORFF,MEGAN         Assistant Professor
    ## 3731                        ZUMBRUNNEN,JOHN                   Professor
    ## 3732                 ZUMWALDE,NICHOLAS ALAN          Asst Faculty Assoc
    ## 3733                     ZURAWSKI,SARAH ANN                    Lecturer
    ## 3734                             ZWASKA,AMY              Assoc Lecturer
    ## 3735                           ZWECK,JORDAN         Associate Professor
    ## 3736                        ZWEIBEL,ELLEN G                   Professor
    ##                              department
    ## 1           Obstetrics &amp; Gynecology
    ## 2                        Anesthesiology
    ## 3                                   Art
    ## 4                              Pharmacy
    ## 5                    Information School
    ## 6                            Psychology
    ## 7                Accting &amp; Info Sys
    ## 8    Atmospheric &amp; Oceanic Sciences
    ## 9                Mechanical Engineering
    ## 10   Atmospheric &amp; Oceanic Sciences
    ## 11                              Nursing
    ## 12                   Information School
    ## 13            Animal And Dairy Sciences
    ## 14                           Psychology
    ## 15              School Of Human Ecology
    ## 16                Afro-American Studies
    ## 17                      Volunteer Staff
    ## 18           Curriculum And Instruction
    ## 19          Engineering Research Center
    ## 20             African Cultural Studies
    ## 21                      Plant Pathology
    ## 22                          Dermatology
    ## 23                 Neurological Surgery
    ## 24       Asian Languages &amp; Cultures
    ## 25       Civil &amp; Environmental Engr
    ## 26                                  Art
    ## 27                             Medicine
    ## 28                          Mathematics
    ## 29                           Law School
    ## 30                            Economics
    ## 31        Engr Professional Development
    ## 32                    Computer Sciences
    ## 33                              Surgery
    ## 34                           Pediatrics
    ## 35        Industrial &amp; Systems Engr
    ## 36                             Oncology
    ## 37    Community &amp; Environ Sociology
    ## 38                    Computer Sciences
    ## 39               Educational Psychology
    ## 40        Industrial &amp; Systems Engr
    ## 41                             Medicine
    ## 42               Spanish And Portuguese
    ## 43     Management &amp; Human Resources
    ## 44                            Economics
    ## 45                      Medical Physics
    ## 46                              English
    ## 47                              Nursing
    ## 48                     Military Science
    ## 49          South Asian Sum Lang Instit
    ## 50                           Psychology
    ## 51                 Neurological Surgery
    ## 52                      Plant Pathology
    ## 53                           Pediatrics
    ## 54                   French And Italian
    ## 55                  Engineering Physics
    ## 56                              English
    ## 57       Electrical &amp; Computer Engr
    ## 58             Gender And Women Studies
    ## 59          Mead Witter School Of Music
    ## 60                     Academic Affairs
    ## 61                            Marketing
    ## 62        Engr Professional Development
    ## 63                     Medical Sciences
    ## 64               Spanish And Portuguese
    ## 65                         Bacteriology
    ## 66                  Integrative Biology
    ## 67                         Biochemistry
    ## 68                                  Art
    ## 69                              English
    ## 70                   Information School
    ## 71                           Statistics
    ## 72    Rehab Psychology &amp; Special Ed
    ## 73                         Bacteriology
    ## 74               Spanish And Portuguese
    ## 75          German, Nordic &amp; Slavic
    ## 76       Electrical &amp; Computer Engr
    ## 77                          Mathematics
    ## 78    Community &amp; Environ Sociology
    ## 79                              Nursing
    ## 80               Mechanical Engineering
    ## 81                 Nutritional Sciences
    ## 82                       Administration
    ## 83                             Medicine
    ## 84                             Medicine
    ## 85                          Kinesiology
    ## 86                            Geography
    ## 87               Mechanical Engineering
    ## 88                     Consumer Science
    ## 89                          Mathematics
    ## 90                          Art History
    ## 91                               Botany
    ## 92                         Bacteriology
    ## 93       Biological Systems Engineering
    ## 94                          Mathematics
    ## 95                     Medical Sciences
    ## 96              School Of Human Ecology
    ## 97                             Agronomy
    ## 98                              Nursing
    ## 99                        Asian Studies
    ## 100                Nutritional Sciences
    ## 101                        Biochemistry
    ## 102         Obstetrics &amp; Gynecology
    ## 103      Engineering Student Developmnt
    ## 104                             History
    ## 105                          Law School
    ## 106   Real Estate &amp; Urgan Land Econ
    ## 107             Comparative Biosciences
    ## 108                             English
    ## 109                         Mathematics
    ## 110              Spanish And Portuguese
    ## 111                  French And Italian
    ## 112                     Volunteer Staff
    ## 113   Materials Science&amp;Engineering
    ## 114                    Small Animal Iii
    ## 115                           Marketing
    ## 116                   Computer Sciences
    ## 117                   Computer Sciences
    ## 118                        Soil Science
    ## 119           Animal And Dairy Sciences
    ## 120                                 Art
    ## 121            Pathobiological Sciences
    ## 122                  Communication Arts
    ## 123             School Of Human Ecology
    ## 124              Biomedical Engineering
    ## 125      Asian Languages &amp; Cultures
    ## 126              Educational Psychology
    ## 127                 Integrative Biology
    ## 128                            Medicine
    ## 129                             Nursing
    ## 130                          Law School
    ## 131                        Biochemistry
    ## 132                        Horticulture
    ## 133              Biomolecular Chemistry
    ## 134  Liberal Arts &amp; Applied Studies
    ## 135                          Psychology
    ## 136                         Dermatology
    ## 137                Madison Microbiology
    ## 138                  Information School
    ## 139                         Kinesiology
    ## 140                          Psychology
    ## 141                           Radiology
    ## 142                   Political Science
    ## 143                   Computer Sciences
    ## 144                            Pharmacy
    ## 145                             English
    ## 146                 Theatre &amp; Drama
    ## 147                          Pediatrics
    ## 148   Operations &amp; Information Mgmt
    ## 149   Materials Science&amp;Engineering
    ## 150                   Computer Sciences
    ## 151                    Medical Sciences
    ## 152                Nutritional Sciences
    ## 153  Atmospheric &amp; Oceanic Sciences
    ## 154      Civil &amp; Environmental Engr
    ## 155                             Physics
    ## 156      Admin:Student Academic Affairs
    ## 157                          Law School
    ## 158                           Geography
    ## 159                             Nursing
    ## 160          Curriculum And Instruction
    ## 161             Comparative Biosciences
    ## 162      Civil Society And Comm Studies
    ## 163                          Psychiatry
    ## 164   Rehab Psychology &amp; Special Ed
    ## 165                             Physics
    ## 166                                 Art
    ## 167                          Psychiatry
    ## 168          Educational Policy Studies
    ## 169               Counseling Psychology
    ## 170               Ft Mba Program Office
    ## 171                 Integrative Biology
    ## 172                        Soil Science
    ## 173                             History
    ## 174                   Computer Sciences
    ## 175                      Anesthesiology
    ## 176                        Soil Science
    ## 177                     Plant Pathology
    ## 178                          Law School
    ## 179            Gender And Women Studies
    ## 180                            Medicine
    ## 181   Sustainability&amp;Global Environ
    ## 182                   Computer Sciences
    ## 183                           Astronomy
    ## 184                             Physics
    ## 185  Agricultural&amp;Applied Economics
    ## 186       Engr Professional Development
    ## 187                Risk &amp; Insurance
    ## 188      Asian Languages &amp; Cultures
    ## 189               Ft Mba Program Office
    ## 190                         Kinesiology
    ## 191                            Pharmacy
    ## 192                     Family Medicine
    ## 193                              Botany
    ## 194                           Sociology
    ## 195                             English
    ## 196                                 Art
    ## 197       Planning &amp; Landscape Arch
    ## 198                           Chemistry
    ## 199             School Of Human Ecology
    ## 200              Accting &amp; Info Sys
    ## 201            Pathobiological Sciences
    ## 202                   Surgical Sciences
    ## 203                          Pediatrics
    ## 204          Educational Policy Studies
    ## 205                 Engineering Physics
    ## 206       Planning &amp; Landscape Arch
    ## 207                            Pharmacy
    ## 208                Neurological Surgery
    ## 209                           Chemistry
    ## 210                         Mathematics
    ## 211   Operations &amp; Information Mgmt
    ## 212             Biology Core Curriculum
    ## 213                          Pediatrics
    ## 214                          Geoscience
    ## 215                Risk &amp; Insurance
    ## 216       Planning &amp; Landscape Arch
    ## 217                              Botany
    ## 218                          Statistics
    ## 219          Population Health Sciences
    ## 220   Operations &amp; Information Mgmt
    ## 221                      Human Oncology
    ## 222                           Neurology
    ## 223             School Of Human Ecology
    ## 224  Agricultural&amp;Applied Economics
    ## 225                     Family Medicine
    ## 226                          Statistics
    ## 227                             English
    ## 228                   Academic Programs
    ## 229                             Physics
    ## 230                    Academic Affairs
    ## 231                                 Art
    ## 232                       Asian Studies
    ## 233                        Biochemistry
    ## 234                     Medical Physics
    ## 235   Pathology&amp;Laboratory Medicine
    ## 236                    Academic Affairs
    ## 237                             English
    ## 238      Electrical &amp; Computer Engr
    ## 239               Counseling Psychology
    ## 240                  Information School
    ## 241         Mead Witter School Of Music
    ## 242              Spanish And Portuguese
    ## 243                         Kinesiology
    ## 244   Community &amp; Environ Sociology
    ## 245       Engr Professional Development
    ## 246              Educational Psychology
    ## 247                         Mathematics
    ## 248                 Integrative Biology
    ## 249                            Medicine
    ## 250                            Medicine
    ## 251   Classic &amp; Ancient Near E Stds
    ## 252                          Philosophy
    ## 253                         Mathematics
    ## 254                          Psychology
    ## 255                          Law School
    ## 256                            Medicine
    ## 257                     Plant Pathology
    ## 258                   Surgical Sciences
    ## 259                             Surgery
    ## 260                         Social Work
    ## 261                             Physics
    ## 262       Forest &amp; Wildlife Ecology
    ## 263          Curriculum And Instruction
    ## 264          Curriculum And Instruction
    ## 265            Pathobiological Sciences
    ## 266                             English
    ## 267       Cooperatives, Univ Center For
    ## 268                          Pediatrics
    ## 269                          Psychology
    ## 270                           Chemistry
    ## 271                           Astronomy
    ## 272              Mechanical Engineering
    ## 273              Biomedical Engineering
    ## 274                 Theatre &amp; Drama
    ## 275                         Kinesiology
    ## 276                           Chemistry
    ## 277   Rehab Psychology &amp; Special Ed
    ## 278                         Amer Ind St
    ## 279                             English
    ## 280                        Horticulture
    ## 281      Ms In Biotechnology Degree Prg
    ## 282       Cell And Regenerative Biology
    ## 283                   Political Science
    ## 284       Industrial &amp; Systems Engr
    ## 285              Spanish And Portuguese
    ## 286                          Law School
    ## 287                      Anesthesiology
    ## 288                          Law School
    ## 289         Obstetrics &amp; Gynecology
    ## 290                          Pediatrics
    ## 291                          Psychiatry
    ## 292                         Social Work
    ## 293   Rehab Psychology &amp; Special Ed
    ## 294                             English
    ## 295                             History
    ## 296          Curriculum And Instruction
    ## 297                   Surgical Sciences
    ## 298                             Physics
    ## 299                           Chemistry
    ## 300                 Integrative Biology
    ## 301                      Anesthesiology
    ## 302                             Nursing
    ## 303         Mead Witter School Of Music
    ## 304               Cals Academic Affairs
    ## 305                        Soil Science
    ## 306                   Surgical Sciences
    ## 307                             History
    ## 308      Civil &amp; Environmental Engr
    ## 309                           Chemistry
    ## 310              Biomedical Engineering
    ## 311                    Academic Affairs
    ## 312                  Information School
    ## 313       Planning &amp; Landscape Arch
    ## 314       Cell And Regenerative Biology
    ## 315      Civil &amp; Environmental Engr
    ## 316                           Marketing
    ## 317      Civil &amp; Environmental Engr
    ## 318        Madison Pathology/Toxicology
    ## 319    Management &amp; Human Resources
    ## 320                         Social Work
    ## 321  Erdman Ctr For Ops &amp; Tech Mgmt
    ## 322       Cell And Regenerative Biology
    ## 323         Obstetrics &amp; Gynecology
    ## 324                   Political Science
    ## 325                         Social Work
    ## 326                     Volunteer Staff
    ## 327                             Physics
    ## 328                        Food Science
    ## 329              Educational Psychology
    ## 330                           Neurology
    ## 331                             Nursing
    ## 332                          Geoscience
    ## 333                 Engineering Physics
    ## 334                     Family Medicine
    ## 335       Engr Professional Development
    ## 336      Electrical &amp; Computer Engr
    ## 337                   Academic Programs
    ## 338   Communication Sci &amp; Disorders
    ## 339         German, Nordic &amp; Slavic
    ## 340                             Physics
    ## 341                        Soil Science
    ## 342                             History
    ## 343                    Integ Liberal St
    ## 344      Electrical &amp; Computer Engr
    ## 345         Life Sciences Communication
    ## 346        Wisconsin School Of Business
    ## 347                         Social Work
    ## 348                          Geoscience
    ## 349        Wisconsin School Of Business
    ## 350                  French And Italian
    ## 351       Industrial &amp; Systems Engr
    ## 352                             English
    ## 353       Forest &amp; Wildlife Ecology
    ## 354                          Law School
    ## 355              Mechanical Engineering
    ## 356                             Nursing
    ## 357                        Anthropology
    ## 358                             English
    ## 359                           Chemistry
    ## 360                           Chemistry
    ## 361                           Radiology
    ## 362                           Marketing
    ## 363                              Botany
    ## 364                             Surgery
    ## 365                            Oncology
    ## 366                      Human Oncology
    ## 367       A.C. Nielsen Ctr For Mkt Rsch
    ## 368                         Kinesiology
    ## 369   Ophthalmology&amp;Visual Sciences
    ## 370         German, Nordic &amp; Slavic
    ## 371                             Physics
    ## 372                            Medicine
    ## 373                             Nursing
    ## 374                          Psychology
    ## 375                         Social Work
    ## 376                              Botany
    ## 377                          Law School
    ## 378                  Information School
    ## 379                          Law School
    ## 380                         Social Work
    ## 381   Real Estate &amp; Urgan Land Econ
    ## 382                   Ctr For Jewish St
    ## 383                 Integrative Biology
    ## 384                            Pharmacy
    ## 385       Cell And Regenerative Biology
    ## 386              Madison Administration
    ## 387                 Integrative Biology
    ## 388               Counseling Psychology
    ## 389                          Philosophy
    ## 390                  Information School
    ## 391                             English
    ## 392                          Law School
    ## 393   Classic &amp; Ancient Near E Stds
    ## 394   Biostatistics&amp;Med Informatics
    ## 395                 Engineering Physics
    ## 396                   Political Science
    ## 397   Pathology&amp;Laboratory Medicine
    ## 398                Neurological Surgery
    ## 399                   Surgical Sciences
    ## 400         Life Sciences Communication
    ## 401                   Surgical Sciences
    ## 402              Biomolecular Chemistry
    ## 403              Educational Psychology
    ## 404                             Finance
    ## 405                          Law School
    ## 406         Obstetrics &amp; Gynecology
    ## 407                         Kinesiology
    ## 408          Population Health Sciences
    ## 409                             Surgery
    ## 410            African Cultural Studies
    ## 411                     Family Medicine
    ## 412                         Social Work
    ## 413                            Genetics
    ## 414                           Chemistry
    ## 415                             Nursing
    ## 416       Forest &amp; Wildlife Ecology
    ## 417                  French And Italian
    ## 418                           Chemistry
    ## 419                          Law School
    ## 420                           Geography
    ## 421               Counseling Psychology
    ## 422                            Pharmacy
    ## 423                           Marketing
    ## 424      Asian Languages &amp; Cultures
    ## 425   Communication Sci &amp; Disorders
    ## 426                                 Art
    ## 427                           Chemistry
    ## 428          Curriculum And Instruction
    ## 429                   Academic Programs
    ## 430                        Anthropology
    ## 431                   Political Science
    ## 432                           Neurology
    ## 433                            Oncology
    ## 434              Accting &amp; Info Sys
    ## 435       Forest &amp; Wildlife Ecology
    ## 436                          Psychology
    ## 437                            Medicine
    ## 438  Human Development&amp;Family Study
    ## 439                         Social Work
    ## 440                             Surgery
    ## 441                            Pharmacy
    ## 442          Population Health Sciences
    ## 443                           Chemistry
    ## 444   Ed Leadership&amp;Policy Analysis
    ## 445                    Medical Sciences
    ## 446                        Bacteriology
    ## 447                   Political Science
    ## 448                         Mathematics
    ## 449                     Family Medicine
    ## 450                            Medicine
    ## 451                             History
    ## 452                        Biochemistry
    ## 453                                 Art
    ## 454         Mead Witter School Of Music
    ## 455                           Economics
    ## 456                             Nursing
    ## 457                    Consumer Science
    ## 458                               Dance
    ## 459           Animal And Dairy Sciences
    ## 460             Comparative Biosciences
    ## 461                         Art History
    ## 462                   Computer Sciences
    ## 463                           Radiology
    ## 464                         Mathematics
    ## 465                        Horticulture
    ## 466         Mead Witter School Of Music
    ## 467                          Psychology
    ## 468                             English
    ## 469                             History
    ## 470         German, Nordic &amp; Slavic
    ## 471                        Anthropology
    ## 472                 Theatre &amp; Drama
    ## 473                              Botany
    ## 474                    Medical Sciences
    ## 475   Real Estate &amp; Urgan Land Econ
    ## 476              Biomedical Engineering
    ## 477            Gender And Women Studies
    ## 478                    Military Science
    ## 479                   Political Science
    ## 480                        Biochemistry
    ## 481              Accting &amp; Info Sys
    ## 482                          Pediatrics
    ## 483                   Computer Sciences
    ## 484       Industrial &amp; Systems Engr
    ## 485                   Computer Sciences
    ## 486                             Surgery
    ## 487                         Kinesiology
    ## 488                          Geoscience
    ## 489             Comparative Biosciences
    ## 490   Ed Leadership&amp;Policy Analysis
    ## 491                             Physics
    ## 492      Civil &amp; Environmental Engr
    ## 493                           Sociology
    ## 494                            Medicine
    ## 495                             History
    ## 496                          Law School
    ## 497                    Medical Sciences
    ## 498                          Geoscience
    ## 499                                 Art
    ## 500                          Law School
    ## 501                             Centers
    ## 502   Journalism&amp;Mass Communication
    ## 503                         Art History
    ## 504                          Law School
    ## 505                             English
    ## 506                             Nursing
    ## 507                            Medicine
    ## 508   Communication Sci &amp; Disorders
    ## 509                           Chemistry
    ## 510                    Medical Sciences
    ## 511         German, Nordic &amp; Slavic
    ## 512                          Pediatrics
    ## 513                    Military Science
    ## 514              Spanish And Portuguese
    ## 515                       Naval Science
    ## 516      Asian Languages &amp; Cultures
    ## 517                           Neurology
    ## 518                             Surgery
    ## 519      Orthopedics And Rehabilitation
    ## 520               Counseling Psychology
    ## 521                             History
    ## 522                           Economics
    ## 523         Mead Witter School Of Music
    ## 524                         Social Work
    ## 525          Department Of Neuroscience
    ## 526                         Mathematics
    ## 527          Nicholas Ctr For Cf&amp;Ib
    ## 528                             Finance
    ## 529                         Dermatology
    ## 530                           Wiscience
    ## 531                            Genetics
    ## 532                         Mathematics
    ## 533          Department Of Neuroscience
    ## 534                            Medicine
    ## 535                          Statistics
    ## 536                         Social Work
    ## 537                          Law School
    ## 538                   Computer Sciences
    ## 539                             English
    ## 540  Agricultural&amp;Applied Economics
    ## 541         German, Nordic &amp; Slavic
    ## 542      Chemical &amp; Biological Engr
    ## 543                   Computer Sciences
    ## 544              Mechanical Engineering
    ## 545                         Mathematics
    ## 546                     Medical Physics
    ## 547   Biostatistics&amp;Med Informatics
    ## 548                         Kinesiology
    ## 549         Life Sciences Communication
    ## 550              Mechanical Engineering
    ## 551                         Mathematics
    ## 552                    Military Science
    ## 553                             History
    ## 554                      Design Studies
    ## 555       Forest &amp; Wildlife Ecology
    ## 556              Biomedical Engineering
    ## 557                            Pharmacy
    ## 558                           Economics
    ## 559                          Statistics
    ## 560                  School For Workers
    ## 561      Lafollette Sch Of Publ Affairs
    ## 562         Life Sciences Communication
    ## 563         Mead Witter School Of Music
    ## 564          Department Of Neuroscience
    ## 565                             English
    ## 566      Biological Systems Engineering
    ## 567                           Chemistry
    ## 568              Accting &amp; Info Sys
    ## 569                         Art History
    ## 570                       Naval Science
    ## 571      Asian Languages &amp; Cultures
    ## 572                 Engineering Physics
    ## 573                               Dance
    ## 574                          Law School
    ## 575          Curriculum And Instruction
    ## 576                     Medical Physics
    ## 577                        Bacteriology
    ## 578   Journalism&amp;Mass Communication
    ## 579                            Pharmacy
    ## 580   Rehab Psychology &amp; Special Ed
    ## 581                    Medical Sciences
    ## 582                             Physics
    ## 583                           Marketing
    ## 584   Biostatistics&amp;Med Informatics
    ## 585              Accting &amp; Info Sys
    ## 586                             History
    ## 587                          Psychiatry
    ## 588      Civil &amp; Environmental Engr
    ## 589                          Psychiatry
    ## 590   Communication Sci &amp; Disorders
    ## 591          Educational Policy Studies
    ## 592             Comparative Biosciences
    ## 593                   Political Science
    ## 594                                 Art
    ## 595                            Medicine
    ## 596                          Psychiatry
    ## 597                         Kinesiology
    ## 598                         Social Work
    ## 599               Afro-American Studies
    ## 600        Madison Pathology/Toxicology
    ## 601                          Philosophy
    ## 602           Animal And Dairy Sciences
    ## 603                           Chemistry
    ## 604                        Anthropology
    ## 605              Spanish And Portuguese
    ## 606                    Academic Affairs
    ## 607      Orthopedics And Rehabilitation
    ## 608                             Nursing
    ## 609          Population Health Sciences
    ## 610                             Nursing
    ## 611      Chemical &amp; Biological Engr
    ## 612                          Pediatrics
    ## 613                          Psychology
    ## 614                 Engineering Physics
    ## 615    Management &amp; Human Resources
    ## 616                          Psychology
    ## 617                          Law School
    ## 618   Communication Sci &amp; Disorders
    ## 619                           Geography
    ## 620                          Law School
    ## 621                            Pharmacy
    ## 622                             Nursing
    ## 623             School Of Human Ecology
    ## 624   Community &amp; Environ Sociology
    ## 625                    Consumer Science
    ## 626            Pathobiological Sciences
    ## 627                          Law School
    ## 628       Cell And Regenerative Biology
    ## 629                   Surgical Sciences
    ## 630                        Horticulture
    ## 631                         Kinesiology
    ## 632                       Dairy Science
    ## 633            Strategic Communications
    ## 634                            Agronomy
    ## 635                         Social Work
    ## 636              Mechanical Engineering
    ## 637   Communication Sci &amp; Disorders
    ## 638   Ed Leadership&amp;Policy Analysis
    ## 639                 Theatre &amp; Drama
    ## 640                  Community Dev Inst
    ## 641                           Sociology
    ## 642                  Communication Arts
    ## 643                           Sociology
    ## 644                         Kinesiology
    ## 645                    Medical Sciences
    ## 646         Mead Witter School Of Music
    ## 647   Biostatistics&amp;Med Informatics
    ## 648              Biomolecular Chemistry
    ## 649                        Bacteriology
    ## 650                             English
    ## 651                         Social Work
    ## 652                   Political Science
    ## 653               Counseling Psychology
    ## 654                             Physics
    ## 655                             Finance
    ## 656                               Dance
    ## 657                         Mathematics
    ## 658              Spanish And Portuguese
    ## 659          Educational Policy Studies
    ## 660                          Psychiatry
    ## 661                    Academic Affairs
    ## 662                 Engineering Physics
    ## 663                           Wiscience
    ## 664              Accting &amp; Info Sys
    ## 665                          Statistics
    ## 666                    European Studies
    ## 667                          Pediatrics
    ## 668                        Biochemistry
    ## 669  Agricultural&amp;Applied Economics
    ## 670                        Biochemistry
    ## 671                          Law School
    ## 672                Risk &amp; Insurance
    ## 673                         Mathematics
    ## 674                        Biochemistry
    ## 675   Communication Sci &amp; Disorders
    ## 676                          Entomology
    ## 677                   Political Science
    ## 678      Civil &amp; Environmental Engr
    ## 679   Biostatistics&amp;Med Informatics
    ## 680            Pathobiological Sciences
    ## 681           Animal And Dairy Sciences
    ## 682   Ed Leadership&amp;Policy Analysis
    ## 683                 Engineering Physics
    ## 684                             History
    ## 685         Mead Witter School Of Music
    ## 686               Ev Mba Program Office
    ## 687                             English
    ## 688   Ophthalmology&amp;Visual Sciences
    ## 689                            Medicine
    ## 690                     Medical Physics
    ## 691                       Asian Studies
    ## 692                   Surgical Sciences
    ## 693   Journalism&amp;Mass Communication
    ## 694                             Physics
    ## 695                        Bacteriology
    ## 696         Mead Witter School Of Music
    ## 697                          Psychology
    ## 698   Community &amp; Environ Sociology
    ## 699               Cals Academic Affairs
    ## 700          Department Of Neuroscience
    ## 701            Pathobiological Sciences
    ## 702                   Computer Sciences
    ## 703      Chemical &amp; Biological Engr
    ## 704                            Pharmacy
    ## 705                          Innovation
    ## 706                         Art History
    ## 707                 Integrative Biology
    ## 708         German, Nordic &amp; Slavic
    ## 709                          Pediatrics
    ## 710                   Computer Sciences
    ## 711                             Physics
    ## 712                          Psychology
    ## 713      Ms In Biotechnology Degree Prg
    ## 714                            Medicine
    ## 715                    Academic Affairs
    ## 716       Engr Professional Development
    ## 717                          Law School
    ## 718               Afro-American Studies
    ## 719      Electrical &amp; Computer Engr
    ## 720                        Horticulture
    ## 721              Spanish And Portuguese
    ## 722                   Surgical Sciences
    ## 723                            Agronomy
    ## 724                            Pharmacy
    ## 725                     Medical Physics
    ## 726        Wisconsin School Of Business
    ## 727                          Pediatrics
    ## 728                Grainger Ctr For Scm
    ## 729                  French And Italian
    ## 730                    Medical Sciences
    ## 731                     Family Medicine
    ## 732              Mechanical Engineering
    ## 733   Operations &amp; Information Mgmt
    ## 734                  French And Italian
    ## 735       Industrial &amp; Systems Engr
    ## 736            Law, Society And Justice
    ## 737                             English
    ## 738  Agricultural&amp;Applied Economics
    ## 739   Communication Sci &amp; Disorders
    ## 740                        Biochemistry
    ## 741      Electrical &amp; Computer Engr
    ## 742                          Geoscience
    ## 743   Biostatistics&amp;Med Informatics
    ## 744                            Medicine
    ## 745                             Finance
    ## 746                Neurological Surgery
    ## 747                          Pediatrics
    ## 748                             Physics
    ## 749                           Economics
    ## 750                         Mathematics
    ## 751   Real Estate &amp; Urgan Land Econ
    ## 752                         Mathematics
    ## 753       Planning &amp; Landscape Arch
    ## 754                             History
    ## 755               Ft Mba Program Office
    ## 756          Department Of Neuroscience
    ## 757              Biomolecular Chemistry
    ## 758                   Computer Sciences
    ## 759  Atmospheric &amp; Oceanic Sciences
    ## 760                          Law School
    ## 761                             History
    ## 762                         Mathematics
    ## 763      Asian Languages &amp; Cultures
    ## 764      Asian Languages &amp; Cultures
    ## 765                          Psychology
    ## 766                     Family Medicine
    ## 767      Orthopedics And Rehabilitation
    ## 768   Biostatistics&amp;Med Informatics
    ## 769                Neurological Surgery
    ## 770                             English
    ## 771                             English
    ## 772                   Computer Sciences
    ## 773                   Computer Sciences
    ## 774                          Pediatrics
    ## 775   Ed Leadership&amp;Policy Analysis
    ## 776                    Medical Sciences
    ## 777                   Pharmacy Outreach
    ## 778                 Engineering Physics
    ## 779                         Social Work
    ## 780          Population Health Sciences
    ## 781                         Kinesiology
    ## 782      Biological Systems Engineering
    ## 783         Mead Witter School Of Music
    ## 784                Medical Microbiology
    ## 785             School Of Human Ecology
    ## 786            African Cultural Studies
    ## 787        Se Asian Summer Studies Inst
    ## 788                            Oncology
    ## 789               Counseling Psychology
    ## 790      Civil Society And Comm Studies
    ## 791                             English
    ## 792         Mead Witter School Of Music
    ## 793                   Computer Sciences
    ## 794         Mead Witter School Of Music
    ## 795             School Of Human Ecology
    ## 796                            Genetics
    ## 797                   Computer Sciences
    ## 798         Mead Witter School Of Music
    ## 799         Mead Witter School Of Music
    ## 800                         Amer Ind St
    ## 801  Agricultural&amp;Applied Economics
    ## 802             School Of Human Ecology
    ## 803                           Astronomy
    ## 804                    Medical Sciences
    ## 805                        Bacteriology
    ## 806                    Medical Sciences
    ## 807                            Pharmacy
    ## 808   Rehab Psychology &amp; Special Ed
    ## 809      Orthopedics And Rehabilitation
    ## 810                   Surgical Sciences
    ## 811   Communication Sci &amp; Disorders
    ## 812  Agricultural&amp;Applied Economics
    ## 813   Journalism&amp;Mass Communication
    ## 814      Lafollette Sch Of Publ Affairs
    ## 815       Forest &amp; Wildlife Ecology
    ## 816                             Nursing
    ## 817                         Social Work
    ## 818   Classic &amp; Ancient Near E Stds
    ## 819              Mechanical Engineering
    ## 820                         Art History
    ## 821      Biological Systems Engineering
    ## 822                             English
    ## 823  Agricultural&amp;Applied Economics
    ## 824         German, Nordic &amp; Slavic
    ## 825         Obstetrics &amp; Gynecology
    ## 826                    Academic Affairs
    ## 827                     Family Medicine
    ## 828                 Integrative Biology
    ## 829      Chemical &amp; Biological Engr
    ## 830                    Medical Sciences
    ## 831                    Academic Affairs
    ## 832             School Of Human Ecology
    ## 833               Ev Mba Program Office
    ## 834                         Social Work
    ## 835                         Social Work
    ## 836      Asian Languages &amp; Cultures
    ## 837          Population Health Sciences
    ## 838      Lafollette Sch Of Publ Affairs
    ## 839            Pathobiological Sciences
    ## 840                          Geoscience
    ## 841                             Nursing
    ## 842                           Sociology
    ## 843                          Law School
    ## 844                         Mathematics
    ## 845                  French And Italian
    ## 846                      Design Studies
    ## 847                           Sociology
    ## 848   Communication Sci &amp; Disorders
    ## 849                          Geoscience
    ## 850                   Surgical Sciences
    ## 851                            Pharmacy
    ## 852    Management &amp; Human Resources
    ## 853                            Medicine
    ## 854                    Academic Affairs
    ## 855                         Social Work
    ## 856      Admin:Student Academic Affairs
    ## 857                           Chemistry
    ## 858               Afro-American Studies
    ## 859                             English
    ## 860         Engineering Research Center
    ## 861                         Kinesiology
    ## 862      Hawk Center For Invst Analysis
    ## 863                         Kinesiology
    ## 864      Lafollette Sch Of Publ Affairs
    ## 865                          Law School
    ## 866                         Social Work
    ## 867              Spanish And Portuguese
    ## 868                             Physics
    ## 869                   Academic Programs
    ## 870                          Pediatrics
    ## 871         Obstetrics &amp; Gynecology
    ## 872                 Integrative Biology
    ## 873                          Psychiatry
    ## 874                Nutritional Sciences
    ## 875   Rehab Psychology &amp; Special Ed
    ## 876                Nutritional Sciences
    ## 877   Communication Sci &amp; Disorders
    ## 878                   Surgical Sciences
    ## 879              Educational Psychology
    ## 880                  French And Italian
    ## 881         German, Nordic &amp; Slavic
    ## 882                          Pediatrics
    ## 883                         Social Work
    ## 884            Pathobiological Sciences
    ## 885                     Medical Physics
    ## 886                          Statistics
    ## 887                         Mathematics
    ## 888      Lafollette Sch Of Publ Affairs
    ## 889   Communication Sci &amp; Disorders
    ## 890                  Communication Arts
    ## 891                           Chemistry
    ## 892                     Medical Physics
    ## 893                        Horticulture
    ## 894        Madison Pathology/Toxicology
    ## 895                           Sociology
    ## 896                     Medical Physics
    ## 897                           Sociology
    ## 898                              Botany
    ## 899                        Horticulture
    ## 900                Risk &amp; Insurance
    ## 901                             Nursing
    ## 902         Mead Witter School Of Music
    ## 903                           Economics
    ## 904          Population Health Sciences
    ## 905                           Sociology
    ## 906              Biomolecular Chemistry
    ## 907            African Cultural Studies
    ## 908                     Medical Physics
    ## 909            Gender And Women Studies
    ## 910              Educational Psychology
    ## 911                        Anthropology
    ## 912                             English
    ## 913   Community &amp; Environ Sociology
    ## 914   Materials Science&amp;Engineering
    ## 915                           Marketing
    ## 916              Accting &amp; Info Sys
    ## 917       Graaskamp Ctr For Real Estate
    ## 918                             Finance
    ## 919         South Asian Sum Lang Instit
    ## 920                             Physics
    ## 921              Mechanical Engineering
    ## 922                          Statistics
    ## 923                          Law School
    ## 924                           Sociology
    ## 925                         Mathematics
    ## 926                             Nursing
    ## 927                  Information School
    ## 928                Nutritional Sciences
    ## 929                            Medicine
    ## 930                           Chemistry
    ## 931                        Food Science
    ## 932                           Economics
    ## 933   Pathology&amp;Laboratory Medicine
    ## 934                             English
    ## 935   Materials Science&amp;Engineering
    ## 936         German, Nordic &amp; Slavic
    ## 937                     Family Medicine
    ## 938                             Physics
    ## 939   Pathology&amp;Laboratory Medicine
    ## 940                            Oncology
    ## 941                         Social Work
    ## 942                     Medical Physics
    ## 943                   Academic Programs
    ## 944      Ms In Biotechnology Degree Prg
    ## 945                           Neurology
    ## 946                Nutritional Sciences
    ## 947                 Theatre &amp; Drama
    ## 948                         Mathematics
    ## 949                             Physics
    ## 950                             Urology
    ## 951   Ed Leadership&amp;Policy Analysis
    ## 952      Electrical &amp; Computer Engr
    ## 953                             English
    ## 954                        Horticulture
    ## 955                             Finance
    ## 956                          Geoscience
    ## 957          Curriculum And Instruction
    ## 958                         Mathematics
    ## 959                            Medicine
    ## 960                           Neurology
    ## 961   Materials Science&amp;Engineering
    ## 962              Accting &amp; Info Sys
    ## 963                         Social Work
    ## 964                   Computer Sciences
    ## 965                              Botany
    ## 966           Animal And Dairy Sciences
    ## 967                           Sociology
    ## 968                   Surgical Sciences
    ## 969                          Geoscience
    ## 970                   Computer Sciences
    ## 971                             Nursing
    ## 972                   Computer Sciences
    ## 973                                #N/A
    ## 974                         Kinesiology
    ## 975                       Asian Studies
    ## 976                          Law School
    ## 977                          Law School
    ## 978   Communication Sci &amp; Disorders
    ## 979                             English
    ## 980              Educational Psychology
    ## 981                          Statistics
    ## 982         Mead Witter School Of Music
    ## 983                            Pharmacy
    ## 984         Life Sciences Communication
    ## 985                         Social Work
    ## 986   Pathology&amp;Laboratory Medicine
    ## 987                                 Art
    ## 988             School Of Human Ecology
    ## 989                                 Art
    ## 990                          Philosophy
    ## 991      Lafollette Sch Of Publ Affairs
    ## 992       Engr Professional Development
    ## 993                            Medicine
    ## 994  Agricultural&amp;Applied Economics
    ## 995                 Engineering Physics
    ## 996              Spanish And Portuguese
    ## 997                            Pharmacy
    ## 998                             Physics
    ## 999                        Bacteriology
    ## 1000                  Surgical Sciences
    ## 1001  Journalism&amp;Mass Communication
    ## 1002                         Pediatrics
    ## 1003                          Radiology
    ## 1004  Communication Sci &amp; Disorders
    ## 1005                         Law School
    ## 1006                       Biochemistry
    ## 1007             Biomolecular Chemistry
    ## 1008                            English
    ## 1009                   Consumer Science
    ## 1010             Mechanical Engineering
    ## 1011                            Surgery
    ## 1012             Mechanical Engineering
    ## 1013                Engineering Physics
    ## 1014                            Nursing
    ## 1015        Administration-Acad Affairs
    ## 1016                        Social Work
    ## 1017                        Social Work
    ## 1018                   Medical Sciences
    ## 1019     Civil &amp; Environmental Engr
    ## 1020     Electrical &amp; Computer Engr
    ## 1021                          Chemistry
    ## 1022                       Soil Science
    ## 1023                          Sociology
    ## 1024              Cals Academic Affairs
    ## 1025         Curriculum And Instruction
    ## 1026          Animal And Dairy Sciences
    ## 1027  Journalism&amp;Mass Communication
    ## 1028                         Law School
    ## 1029                          Economics
    ## 1030                            English
    ## 1031           Pathobiological Sciences
    ## 1032           Pathobiological Sciences
    ## 1033                       Biochemistry
    ## 1034  Pathology&amp;Laboratory Medicine
    ## 1035              Counseling Psychology
    ## 1036                          Economics
    ## 1037                        Mathematics
    ## 1038             Accting &amp; Info Sys
    ## 1039                          Sociology
    ## 1040        Mead Witter School Of Music
    ## 1041     Ms In Biotechnology Degree Prg
    ## 1042                            Surgery
    ## 1043                 Information School
    ## 1044                Theatre &amp; Drama
    ## 1045         Curriculum And Instruction
    ## 1046  Classic &amp; Ancient Near E Stds
    ## 1047            School Of Human Ecology
    ## 1048                  Academic Programs
    ## 1049             Accting &amp; Info Sys
    ## 1050                            Nursing
    ## 1051                           Medicine
    ## 1052                          Neurology
    ## 1053                           Pharmacy
    ## 1054                         Psychology
    ## 1055                           Medicine
    ## 1056                            Nursing
    ## 1057  Ophthalmology&amp;Visual Sciences
    ## 1058                Integrative Biology
    ## 1059   Management &amp; Human Resources
    ## 1060                  Political Science
    ## 1061         Population Health Sciences
    ## 1062                           Pharmacy
    ## 1063                          Geography
    ## 1064                          Chemistry
    ## 1065             Educational Psychology
    ## 1066                         Statistics
    ## 1067                        Social Work
    ## 1068     Lafollette Sch Of Publ Affairs
    ## 1069  Community &amp; Environ Sociology
    ## 1070                        Kinesiology
    ## 1071                          Geography
    ## 1072                           Genetics
    ## 1073           Pathobiological Sciences
    ## 1074           Gender And Women Studies
    ## 1075                        Kinesiology
    ## 1076     Civil &amp; Environmental Engr
    ## 1077                              Dance
    ## 1078      Cell And Regenerative Biology
    ## 1079     Chemical &amp; Biological Engr
    ## 1080                Engineering Physics
    ## 1081                          Chemistry
    ## 1082                         Law School
    ## 1083      Planning &amp; Landscape Arch
    ## 1084              Inst Reg Intl Studies
    ## 1085                                Art
    ## 1086                        Mathematics
    ## 1087     Ms In Biotechnology Degree Prg
    ## 1088                        Social Work
    ## 1089                          Sociology
    ## 1090   Management &amp; Human Resources
    ## 1091                         Pediatrics
    ## 1092                         Psychology
    ## 1093                    Plant Pathology
    ## 1094     Asian Languages &amp; Cultures
    ## 1095             Mechanical Engineering
    ## 1096         Curriculum And Instruction
    ## 1097                          Geography
    ## 1098                         Philosophy
    ## 1099                            Nursing
    ## 1100                           Pharmacy
    ## 1101           Office Of Sustainability
    ## 1102                            Physics
    ## 1103                         Statistics
    ## 1104        Engineering Research Center
    ## 1105                Integrative Biology
    ## 1106                            English
    ## 1107      Planning &amp; Landscape Arch
    ## 1108                             Botany
    ## 1109     Civil &amp; Environmental Engr
    ## 1110                         Psychology
    ## 1111                 Information School
    ## 1112                 French And Italian
    ## 1113  Biostatistics&amp;Med Informatics
    ## 1114                             Botany
    ## 1115        Mead Witter School Of Music
    ## 1116                        Social Work
    ## 1117                          Economics
    ## 1118                         Law School
    ## 1119                  Computer Sciences
    ## 1120                         Law School
    ## 1121 Agricultural&amp;Applied Economics
    ## 1122              Counseling Psychology
    ## 1123                            History
    ## 1124        German, Nordic &amp; Slavic
    ## 1125                           Medicine
    ## 1126                          Geography
    ## 1127                     Design Studies
    ## 1128                            Finance
    ## 1129  Ed Leadership&amp;Policy Analysis
    ## 1130                        Mathematics
    ## 1131  Classic &amp; Ancient Near E Stds
    ## 1132                          Sociology
    ## 1133              Counseling Psychology
    ## 1134           Pathobiological Sciences
    ## 1135                           Medicine
    ## 1136                           Pharmacy
    ## 1137             Spanish And Portuguese
    ## 1138                       Horticulture
    ## 1139                         Psychology
    ## 1140                          Chemistry
    ## 1141           Gender And Women Studies
    ## 1142            Comparative Biosciences
    ## 1143         Curriculum And Instruction
    ## 1144  Dept Of Med History&amp;Bioethics
    ## 1145         Department Of Neuroscience
    ## 1146                    Volunteer Staff
    ## 1147             Biomedical Engineering
    ## 1148                        Mathematics
    ## 1149        Mead Witter School Of Music
    ## 1150         Educational Policy Studies
    ## 1151                         Psychology
    ## 1152                 French And Italian
    ## 1153                         Geoscience
    ## 1154  Materials Science&amp;Engineering
    ## 1155                        Mathematics
    ## 1156                          Marketing
    ## 1157                         Philosophy
    ## 1158     Ms In Biotechnology Degree Prg
    ## 1159                       Bacteriology
    ## 1160        Mead Witter School Of Music
    ## 1161                  Computer Sciences
    ## 1162                             Botany
    ## 1163     Chemical &amp; Biological Engr
    ## 1164              Counseling Psychology
    ## 1165 Agricultural&amp;Applied Economics
    ## 1166                                Art
    ## 1167 International Studies&amp;Programs
    ## 1168                   Medical Sciences
    ## 1169         Curriculum And Instruction
    ## 1170                          Sociology
    ## 1171                            History
    ## 1172                       Biochemistry
    ## 1173                         Entomology
    ## 1174         Curriculum And Instruction
    ## 1175  Journalism&amp;Mass Communication
    ## 1176                  Academic Programs
    ## 1177                 Communication Arts
    ## 1178                Theatre &amp; Drama
    ## 1179                         Psychology
    ## 1180                         Statistics
    ## 1181         Population Health Sciences
    ## 1182     Chemical &amp; Biological Engr
    ## 1183              Afro-American Studies
    ## 1184                         Law School
    ## 1185                            Nursing
    ## 1186                        Social Work
    ## 1187   Management &amp; Human Resources
    ## 1188                          Economics
    ## 1189             Accting &amp; Info Sys
    ## 1190      Cell And Regenerative Biology
    ## 1191             Accting &amp; Info Sys
    ## 1192             Accting &amp; Info Sys
    ## 1193                                Art
    ## 1194                Integrative Biology
    ## 1195                        Mathematics
    ## 1196                         Law School
    ## 1197               Nutritional Sciences
    ## 1198                          Sociology
    ## 1199     Electrical &amp; Computer Engr
    ## 1200                         Law School
    ## 1201                        Social Work
    ## 1202        German, Nordic &amp; Slavic
    ## 1203                   Academic Affairs
    ## 1204                         Entomology
    ## 1205                        Kinesiology
    ## 1206                            English
    ## 1207     Electrical &amp; Computer Engr
    ## 1208                         Entomology
    ## 1209                           Pharmacy
    ## 1210              Counseling Psychology
    ## 1211               Medical Microbiology
    ## 1212     Biological Systems Engineering
    ## 1213                 Communication Arts
    ## 1214                        Mathematics
    ## 1215          Animal And Dairy Sciences
    ## 1216                        Mathematics
    ## 1217                  Computer Sciences
    ## 1218                         Law School
    ## 1219                        Mathematics
    ## 1220                           Pharmacy
    ## 1221                 Emergency Medicine
    ## 1222                          Chemistry
    ## 1223                           Agronomy
    ## 1224                            English
    ## 1225                   Academic Affairs
    ## 1226      Engr Professional Development
    ## 1227            Comparative Biosciences
    ## 1228  Materials Science&amp;Engineering
    ## 1229     Biological Systems Engineering
    ## 1230     Asian Languages &amp; Cultures
    ## 1231                Theatre &amp; Drama
    ## 1232      Planning &amp; Landscape Arch
    ## 1233  Pathology&amp;Laboratory Medicine
    ## 1234                           Pharmacy
    ## 1235                            English
    ## 1236             Educational Psychology
    ## 1237     Electrical &amp; Computer Engr
    ## 1238                         Law School
    ## 1239             Biomedical Engineering
    ## 1240                Theatre &amp; Drama
    ## 1241          Animal And Dairy Sciences
    ## 1242                           Medicine
    ## 1243                   Academic Affairs
    ## 1244  Journalism&amp;Mass Communication
    ## 1245                            English
    ## 1246                            History
    ## 1247                    Medical Physics
    ## 1248                    Family Medicine
    ## 1249                Integrative Biology
    ## 1250                            Nursing
    ## 1251            School Of Human Ecology
    ## 1252                  Computer Sciences
    ## 1253         Curriculum And Instruction
    ## 1254  Ed Leadership&amp;Policy Analysis
    ## 1255                            Physics
    ## 1256                          Chemistry
    ## 1257     Civil &amp; Environmental Engr
    ## 1258     Uw Comprehensive Cancer Center
    ## 1259  Real Estate &amp; Urgan Land Econ
    ## 1260                    Plant Pathology
    ## 1261                        Mathematics
    ## 1262               Neurological Surgery
    ## 1263     Civil &amp; Environmental Engr
    ## 1264                         Law School
    ## 1265                            History
    ## 1266                          Economics
    ## 1267                          Economics
    ## 1268                           Medicine
    ## 1269                          Economics
    ## 1270                            Nursing
    ## 1271                            Physics
    ## 1272                         Law School
    ## 1273                Integrative Biology
    ## 1274        German, Nordic &amp; Slavic
    ## 1275                         Psychology
    ## 1276                  Surgical Sciences
    ## 1277                Integrative Biology
    ## 1278                         Pediatrics
    ## 1279            School Of Human Ecology
    ## 1280               Nutritional Sciences
    ## 1281                   Consumer Science
    ## 1282     Civil &amp; Environmental Engr
    ## 1283      Planning &amp; Landscape Arch
    ## 1284                              Dance
    ## 1285            Biology Core Curriculum
    ## 1286                            English
    ## 1287             Biomolecular Chemistry
    ## 1288      Forest &amp; Wildlife Ecology
    ## 1289                       Food Science
    ## 1290                       Soil Science
    ## 1291        Obstetrics &amp; Gynecology
    ## 1292  Pathology&amp;Laboratory Medicine
    ## 1293            School Of Human Ecology
    ## 1294  Communication Sci &amp; Disorders
    ## 1295                    Family Medicine
    ## 1296                Integrative Biology
    ## 1297                  Surgical Sciences
    ## 1298            School Of Human Ecology
    ## 1299                            Physics
    ## 1300         Curriculum And Instruction
    ## 1301                  Computer Sciences
    ## 1302  Journalism&amp;Mass Communication
    ## 1303        Student Acad Affairs Office
    ## 1304                          Geography
    ## 1305  Operations &amp; Information Mgmt
    ## 1306                       Horticulture
    ## 1307         Curriculum And Instruction
    ## 1308                  Surgical Sciences
    ## 1309                       Anthropology
    ## 1310                            Nursing
    ## 1311                                Art
    ## 1312  Operations &amp; Information Mgmt
    ## 1313                              Dance
    ## 1314                        Kinesiology
    ## 1315                            History
    ## 1316                           Pharmacy
    ## 1317                        Social Work
    ## 1318        Student Acad Affairs Office
    ## 1319                          Marketing
    ## 1320                         Law School
    ## 1321                   Medical Sciences
    ## 1322      Engr Professional Development
    ## 1323                Engineering Physics
    ## 1324                          Marketing
    ## 1325                          Marketing
    ## 1326                        Social Work
    ## 1327     Orthopedics And Rehabilitation
    ## 1328                  Computer Sciences
    ## 1329                      Naval Science
    ## 1330                         Law School
    ## 1331                              Dance
    ## 1332                          Astronomy
    ## 1333           Disease Prevention Admin
    ## 1334                           Medicine
    ## 1335             Mechanical Engineering
    ## 1336                Engineering Physics
    ## 1337                        Social Work
    ## 1338                         Pediatrics
    ## 1339 Atmospheric &amp; Oceanic Sciences
    ## 1340                          Marketing
    ## 1341                         Law School
    ## 1342                          Economics
    ## 1343            Acad Affairs &amp; Prog
    ## 1344          Language Sciences Program
    ## 1345                  Academic Programs
    ## 1346  Communication Sci &amp; Disorders
    ## 1347                            Nursing
    ## 1348                         Psychology
    ## 1349                  Surgical Sciences
    ## 1350                       Biochemistry
    ## 1351                        Mathematics
    ## 1352              Counseling Psychology
    ## 1353  Journalism&amp;Mass Communication
    ## 1354                          Chemistry
    ## 1355                Engineering Physics
    ## 1356          Animal And Dairy Sciences
    ## 1357             Spanish And Portuguese
    ## 1358                    Medical Physics
    ## 1359                          Radiology
    ## 1360                            Physics
    ## 1361  Operations &amp; Information Mgmt
    ## 1362                                Art
    ## 1363                  Political Science
    ## 1364                         Psychiatry
    ## 1365            Comparative Biosciences
    ## 1366                       Bacteriology
    ## 1367                            Nursing
    ## 1368              Afro-American Studies
    ## 1369                     Design Studies
    ## 1370                 Emergency Medicine
    ## 1371        Mead Witter School Of Music
    ## 1372                  Computer Sciences
    ## 1373     Civil &amp; Environmental Engr
    ## 1374                        Social Work
    ## 1375                           Pharmacy
    ## 1376             Spanish And Portuguese
    ## 1377     Hawk Center For Invst Analysis
    ## 1378                    Family Medicine
    ## 1379                          Chemistry
    ## 1380      Vp Diversity And Climate Prog
    ## 1381  Ed Leadership&amp;Policy Analysis
    ## 1382                        Kinesiology
    ## 1383      Engr Professional Development
    ## 1384                                Art
    ## 1385                            Nursing
    ## 1386      Engr Professional Development
    ## 1387                            History
    ## 1388                                Art
    ## 1389 Atmospheric &amp; Oceanic Sciences
    ## 1390     Electrical &amp; Computer Engr
    ## 1391           Pathobiological Sciences
    ## 1392                           Genetics
    ## 1393                 Emergency Medicine
    ## 1394         Curriculum And Instruction
    ## 1395                      Asian Amer St
    ## 1396      Engr Professional Development
    ## 1397                          Marketing
    ## 1398                            Surgery
    ## 1399                                Art
    ## 1400      Vp Diversity And Climate Prog
    ## 1401        Obstetrics &amp; Gynecology
    ## 1402           Pathobiological Sciences
    ## 1403     Electrical &amp; Computer Engr
    ## 1404                        Social Work
    ## 1405                          Chemistry
    ## 1406       Wisconsin School Of Business
    ## 1407                       Biochemistry
    ## 1408                              Dance
    ## 1409                    Plant Pathology
    ## 1410                  Academic Programs
    ## 1411                  Surgical Sciences
    ## 1412                   Medical Sciences
    ## 1413              Ex Mba Program Office
    ## 1414                           Medicine
    ## 1415                           Pharmacy
    ## 1416   Management &amp; Human Resources
    ## 1417     Civil &amp; Environmental Engr
    ## 1418                          Chemistry
    ## 1419  Ophthalmology&amp;Visual Sciences
    ## 1420                     Design Studies
    ## 1421 Liberal Arts &amp; Applied Studies
    ## 1422            Comparative Biosciences
    ## 1423           Disease Prevention Admin
    ## 1424                  Academic Programs
    ## 1425                       Biochemistry
    ## 1426                             Botany
    ## 1427           Gender And Women Studies
    ## 1428                          Economics
    ## 1429                 Communication Arts
    ## 1430      Forest &amp; Wildlife Ecology
    ## 1431                          Chemistry
    ## 1432      Planning &amp; Landscape Arch
    ## 1433                 Communication Arts
    ## 1434              Counseling Psychology
    ## 1435                           Medicine
    ## 1436                            History
    ## 1437                          Neurology
    ## 1438                  Computer Sciences
    ## 1439                           Pharmacy
    ## 1440  Materials Science&amp;Engineering
    ## 1441                           Pharmacy
    ## 1442     Electrical &amp; Computer Engr
    ## 1443                       Soil Science
    ## 1444                            English
    ## 1445                          Geography
    ## 1446                        Mathematics
    ## 1447         Department Of Neuroscience
    ## 1448                          Neurology
    ## 1449   Management &amp; Human Resources
    ## 1450                Integrative Biology
    ## 1451             Educational Psychology
    ## 1452     Chemical &amp; Biological Engr
    ## 1453                                Art
    ## 1454         Curriculum And Instruction
    ## 1455             Biomolecular Chemistry
    ## 1456                         Law School
    ## 1457                    Family Medicine
    ## 1458                     Design Studies
    ## 1459     Asian Languages &amp; Cultures
    ## 1460     Civil &amp; Environmental Engr
    ## 1461  Communication Sci &amp; Disorders
    ## 1462                 Information School
    ## 1463             Spanish And Portuguese
    ## 1464                           Pharmacy
    ## 1465                         Pediatrics
    ## 1466  Classic &amp; Ancient Near E Stds
    ## 1467                            English
    ## 1468                       Food Science
    ## 1469                         Psychology
    ## 1470        Mead Witter School Of Music
    ## 1471                 School For Workers
    ## 1472                         Law School
    ## 1473                            History
    ## 1474                        Mathematics
    ## 1475                           Genetics
    ## 1476                       Food Science
    ## 1477                           Pharmacy
    ## 1478                 Information School
    ## 1479                       Food Science
    ## 1480       Se Asian Summer Studies Inst
    ## 1481           Gender And Women Studies
    ## 1482                 Information School
    ## 1483                            English
    ## 1484               Neurological Surgery
    ## 1485                        Mathematics
    ## 1486                Integrative Biology
    ## 1487                     Human Oncology
    ## 1488              Counseling Psychology
    ## 1489              Counseling Psychology
    ## 1490            Comparative Biosciences
    ## 1491                   Academic Affairs
    ## 1492  Ed Leadership&amp;Policy Analysis
    ## 1493         Department Of Neuroscience
    ## 1494                           Agronomy
    ## 1495             Mechanical Engineering
    ## 1496                            Nursing
    ## 1497                   Academic Affairs
    ## 1498                   Medical Sciences
    ## 1499                 Communication Arts
    ## 1500     Lafollette Sch Of Publ Affairs
    ## 1501     Electrical &amp; Computer Engr
    ## 1502                           Medicine
    ## 1503                            Urology
    ## 1504            School Of Human Ecology
    ## 1505                 Communication Arts
    ## 1506      Cell And Regenerative Biology
    ## 1507             Educational Psychology
    ## 1508              Ft Mba Program Office
    ## 1509                 Information School
    ## 1510                          Sociology
    ## 1511                Integrative Biology
    ## 1512     Asian Languages &amp; Cultures
    ## 1513                    Medical Physics
    ## 1514                      Asian Amer St
    ## 1515                  Computer Sciences
    ## 1516     Electrical &amp; Computer Engr
    ## 1517                            Surgery
    ## 1518                           Pharmacy
    ## 1519                 Information School
    ## 1520                 Bba Program Office
    ## 1521                          Chemistry
    ## 1522     Electrical &amp; Computer Engr
    ## 1523                            Finance
    ## 1524                           Medicine
    ## 1525              Ev Mba Program Office
    ## 1526                            English
    ## 1527                  Academic Programs
    ## 1528                  Surgical Sciences
    ## 1529                Air Force Aerospace
    ## 1530                          Economics
    ## 1531                 Communication Arts
    ## 1532                       Bacteriology
    ## 1533                           Pharmacy
    ## 1534                 Communication Arts
    ## 1535        Mead Witter School Of Music
    ## 1536                    Medical Physics
    ## 1537           Gender And Women Studies
    ## 1538                            English
    ## 1539  Ed Leadership&amp;Policy Analysis
    ## 1540  Real Estate &amp; Urgan Land Econ
    ## 1541               Nutritional Sciences
    ## 1542               Nutritional Sciences
    ## 1543               Risk &amp; Insurance
    ## 1544         Population Health Sciences
    ## 1545            Comparative Biosciences
    ## 1546                           Medicine
    ## 1547                            History
    ## 1548     Lafollette Sch Of Publ Affairs
    ## 1549 Agricultural&amp;Applied Economics
    ## 1550                 Community Dev Inst
    ## 1551                Theatre &amp; Drama
    ## 1552                   Consumer Science
    ## 1553     Asian Languages &amp; Cultures
    ## 1554                          Neurology
    ## 1555                            Nursing
    ## 1556         Department Of Neuroscience
    ## 1557                                Art
    ## 1558                                Art
    ## 1559                  Academic Services
    ## 1560                             Botany
    ## 1561                           Medicine
    ## 1562            Comparative Biosciences
    ## 1563      Engr Professional Development
    ## 1564                            English
    ## 1565                            Physics
    ## 1566  Rehab Psychology &amp; Special Ed
    ## 1567                              Dance
    ## 1568   Ctr For Brand &amp; Product Mgmt
    ## 1569                       Horticulture
    ## 1570                   Academic Affairs
    ## 1571                            Surgery
    ## 1572              Counseling Psychology
    ## 1573                    Plant Pathology
    ## 1574                              Dance
    ## 1575                           Agronomy
    ## 1576                           Agronomy
    ## 1577                           Medicine
    ## 1578                          Geography
    ## 1579                           Medicine
    ## 1580               Medical Microbiology
    ## 1581                           Oncology
    ## 1582                   Academic Affairs
    ## 1583                         Psychiatry
    ## 1584                         Psychiatry
    ## 1585                   Consumer Science
    ## 1586            School Of Human Ecology
    ## 1587             Educational Psychology
    ## 1588     Civil &amp; Environmental Engr
    ## 1589      Engr Professional Development
    ## 1590                           Medicine
    ## 1591         Population Health Sciences
    ## 1592                            Nursing
    ## 1593                         Statistics
    ## 1594      Cell And Regenerative Biology
    ## 1595     Engineering Student Developmnt
    ## 1596                            History
    ## 1597                 Information School
    ## 1598             Educational Psychology
    ## 1599                           Pharmacy
    ## 1600                  Political Science
    ## 1601              Counseling Psychology
    ## 1602      Forest &amp; Wildlife Ecology
    ## 1603                            Physics
    ## 1604        Mead Witter School Of Music
    ## 1605        German, Nordic &amp; Slavic
    ## 1606     Biological Systems Engineering
    ## 1607      Engr Professional Development
    ## 1608        Mead Witter School Of Music
    ## 1609                         Law School
    ## 1610                       Bacteriology
    ## 1611                         Law School
    ## 1612                         Pediatrics
    ## 1613                   Consumer Science
    ## 1614     Electrical &amp; Computer Engr
    ## 1615  Communication Sci &amp; Disorders
    ## 1616                  Academic Programs
    ## 1617           Pathobiological Sciences
    ## 1618  Materials Science&amp;Engineering
    ## 1619          Animal And Dairy Sciences
    ## 1620     Civil &amp; Environmental Engr
    ## 1621                        Social Work
    ## 1622                            Nursing
    ## 1623             Biomolecular Chemistry
    ## 1624                  Political Science
    ## 1625                             Botany
    ## 1626            School Of Human Ecology
    ## 1627                        Dermatology
    ## 1628                   Medical Sciences
    ## 1629                         Statistics
    ## 1630                         Statistics
    ## 1631  Dept Of Med History&amp;Bioethics
    ## 1632              Counseling Psychology
    ## 1633               Medical Microbiology
    ## 1634  Dept Of Med History&amp;Bioethics
    ## 1635  Ed Leadership&amp;Policy Analysis
    ## 1636                         Law School
    ## 1637                            English
    ## 1638                   Medical Sciences
    ## 1639  Communication Sci &amp; Disorders
    ## 1640 Liberal Arts &amp; Applied Studies
    ## 1641                         Geoscience
    ## 1642                          Economics
    ## 1643                         Law School
    ## 1644             Educational Psychology
    ## 1645      Planning &amp; Landscape Arch
    ## 1646                        Mathematics
    ## 1647         Educational Policy Studies
    ## 1648  Biostatistics&amp;Med Informatics
    ## 1649                          Economics
    ## 1650                            History
    ## 1651                            Nursing
    ## 1652                           Oncology
    ## 1653       Wisconsin School Of Business
    ## 1654                       Anthropology
    ## 1655                        Mathematics
    ## 1656                         Law School
    ## 1657                            English
    ## 1658     Asian Languages &amp; Cultures
    ## 1659            School Of Human Ecology
    ## 1660                         Statistics
    ## 1661           Law, Society And Justice
    ## 1662  Real Estate &amp; Urgan Land Econ
    ## 1663        South Asian Sum Lang Instit
    ## 1664  Operations &amp; Information Mgmt
    ## 1665          Animal And Dairy Sciences
    ## 1666     Asian Languages &amp; Cultures
    ## 1667             Educational Psychology
    ## 1668                    Family Medicine
    ## 1669                   Academic Affairs
    ## 1670                        Social Work
    ## 1671                           Medicine
    ## 1672                            Nursing
    ## 1673             Biomolecular Chemistry
    ## 1674             Educational Psychology
    ## 1675                        Mathematics
    ## 1676                            History
    ## 1677     Asian Languages &amp; Cultures
    ## 1678             Educational Psychology
    ## 1679                 Information School
    ## 1680  Biostatistics&amp;Med Informatics
    ## 1681                            History
    ## 1682                       Anthropology
    ## 1683  Operations &amp; Information Mgmt
    ## 1684                  Computer Sciences
    ## 1685         Curriculum And Instruction
    ## 1686  Journalism&amp;Mass Communication
    ## 1687     Electrical &amp; Computer Engr
    ## 1688                       Biochemistry
    ## 1689             Accting &amp; Info Sys
    ## 1690                           Medicine
    ## 1691                     Human Oncology
    ## 1692                           Medicine
    ## 1693                            Nursing
    ## 1694  Ed Leadership&amp;Policy Analysis
    ## 1695              Ex Mba Program Office
    ## 1696             Biomedical Engineering
    ## 1697                            Nursing
    ## 1698                            History
    ## 1699     Electrical &amp; Computer Engr
    ## 1700                       Biochemistry
    ## 1701         Curriculum And Instruction
    ## 1702         Curriculum And Instruction
    ## 1703                      Asian Studies
    ## 1704            School Of Human Ecology
    ## 1705          Animal And Dairy Sciences
    ## 1706                          Economics
    ## 1707             Biomolecular Chemistry
    ## 1708     Admin:Student Academic Affairs
    ## 1709                          Radiology
    ## 1710         Curriculum And Instruction
    ## 1711                            History
    ## 1712                         Pediatrics
    ## 1713                          Radiology
    ## 1714             Educational Psychology
    ## 1715                         Law School
    ## 1716     Chemical &amp; Biological Engr
    ## 1717        German, Nordic &amp; Slavic
    ## 1718                         Law School
    ## 1719     Electrical &amp; Computer Engr
    ## 1720                          Radiology
    ## 1721  Ophthalmology&amp;Visual Sciences
    ## 1722               Medical Microbiology
    ## 1723                    Volunteer Staff
    ## 1724                         Law School
    ## 1725                            Nursing
    ## 1726                    Plant Pathology
    ## 1727                            History
    ## 1728                            English
    ## 1729                         Psychiatry
    ## 1730        Mead Witter School Of Music
    ## 1731             Mechanical Engineering
    ## 1732     Lafollette Sch Of Publ Affairs
    ## 1733                            Physics
    ## 1734                            Nursing
    ## 1735                        Kinesiology
    ## 1736                        Social Work
    ## 1737                           Medicine
    ## 1738                         Psychology
    ## 1739                           Pharmacy
    ## 1740     Electrical &amp; Computer Engr
    ## 1741                              Dance
    ## 1742                          Radiology
    ## 1743                         Law School
    ## 1744                          Wiscience
    ## 1745                          Neurology
    ## 1746                          Astronomy
    ## 1747  Materials Science&amp;Engineering
    ## 1748                  Computer Sciences
    ## 1749            Biology Core Curriculum
    ## 1750                   Medical Sciences
    ## 1751         Curriculum And Instruction
    ## 1752                   Academic Affairs
    ## 1753     Electrical &amp; Computer Engr
    ## 1754                         Law School
    ## 1755                     Anesthesiology
    ## 1756                        Kinesiology
    ## 1757         Curriculum And Instruction
    ## 1758         Curriculum And Instruction
    ## 1759             Biomedical Engineering
    ## 1760  Dept Of Med History&amp;Bioethics
    ## 1761     Electrical &amp; Computer Engr
    ## 1762  Communication Sci &amp; Disorders
    ## 1763        German, Nordic &amp; Slavic
    ## 1764                          Marketing
    ## 1765  Communication Sci &amp; Disorders
    ## 1766      Forest &amp; Wildlife Ecology
    ## 1767                            Nursing
    ## 1768             Mechanical Engineering
    ## 1769                       Horticulture
    ## 1770                            Nursing
    ## 1771                           Agronomy
    ## 1772     Civil &amp; Environmental Engr
    ## 1773               Nutritional Sciences
    ## 1774                        Social Work
    ## 1775                  Computer Sciences
    ## 1776                         Pediatrics
    ## 1777              Counseling Psychology
    ## 1778                        Kinesiology
    ## 1779                            English
    ## 1780     Lafollette Sch Of Publ Affairs
    ## 1781            Comparative Biosciences
    ## 1782                            Nursing
    ## 1783                       Bacteriology
    ## 1784                     Design Studies
    ## 1785   Management &amp; Human Resources
    ## 1786                           Pharmacy
    ## 1787                     Design Studies
    ## 1788                            Nursing
    ## 1789                         Psychiatry
    ## 1790                        Mathematics
    ## 1791                           Pharmacy
    ## 1792                        Mathematics
    ## 1793                  Political Science
    ## 1794               Nutritional Sciences
    ## 1795      Engr Professional Development
    ## 1796     Ms In Biotechnology Degree Prg
    ## 1797                       Soil Science
    ## 1798                   Military Science
    ## 1799                          Radiology
    ## 1800  Materials Science&amp;Engineering
    ## 1801                            English
    ## 1802      Planning &amp; Landscape Arch
    ## 1803      Engr Professional Development
    ## 1804               Nutritional Sciences
    ## 1805                            English
    ## 1806                Engineering Physics
    ## 1807                           Oncology
    ## 1808                           Medicine
    ## 1809                          Chemistry
    ## 1810                    Volunteer Staff
    ## 1811  Real Estate &amp; Urgan Land Econ
    ## 1812                       Biochemistry
    ## 1813                          Chemistry
    ## 1814                           Medicine
    ## 1815             General Administration
    ## 1816                                Art
    ## 1817                Theatre &amp; Drama
    ## 1818                    Plant Pathology
    ## 1819                        Social Work
    ## 1820                            History
    ## 1821                            Finance
    ## 1822             Accting &amp; Info Sys
    ## 1823     Engineering Student Developmnt
    ## 1824          Animal And Dairy Sciences
    ## 1825                             Botany
    ## 1826                  Academic Programs
    ## 1827                 Information School
    ## 1828                        Social Work
    ## 1829                        Kinesiology
    ## 1830  Ophthalmology&amp;Visual Sciences
    ## 1831           Pathobiological Sciences
    ## 1832        German, Nordic &amp; Slavic
    ## 1833       Wisconsin School Of Business
    ## 1834                        Social Work
    ## 1835                          Astronomy
    ## 1836                           Genetics
    ## 1837                           Pharmacy
    ## 1838        Mead Witter School Of Music
    ## 1839                            Nursing
    ## 1840                           Medicine
    ## 1841                            Physics
    ## 1842    Comp Lit &amp; Folklore Studies
    ## 1843                          Astronomy
    ## 1844                            Surgery
    ## 1845                            Nursing
    ## 1846 Atmospheric &amp; Oceanic Sciences
    ## 1847  Dept Of Med History&amp;Bioethics
    ## 1848      Planning &amp; Landscape Arch
    ## 1849        Mead Witter School Of Music
    ## 1850                Integrative Biology
    ## 1851     Asian Languages &amp; Cultures
    ## 1852                        Kinesiology
    ## 1853                        Mathematics
    ## 1854                                Art
    ## 1855      Industrial &amp; Systems Engr
    ## 1856                    Family Medicine
    ## 1857     Electrical &amp; Computer Engr
    ## 1858           Pathobiological Sciences
    ## 1859  Communication Sci &amp; Disorders
    ## 1860         Educational Policy Studies
    ## 1861              Counseling Psychology
    ## 1862      Cell And Regenerative Biology
    ## 1863                                Art
    ## 1864                            Finance
    ## 1865                  Computer Sciences
    ## 1866                           Pharmacy
    ## 1867                  Political Science
    ## 1868                       Anthropology
    ## 1869  Rehab Psychology &amp; Special Ed
    ## 1870           Gender And Women Studies
    ## 1871         Curriculum And Instruction
    ## 1872                        Mathematics
    ## 1873           Pathobiological Sciences
    ## 1874                          Economics
    ## 1875                  Surgical Sciences
    ## 1876          Animal And Dairy Sciences
    ## 1877                       Anthropology
    ## 1878           Pathobiological Sciences
    ## 1879     Electrical &amp; Computer Engr
    ## 1880                        Mathematics
    ## 1881     Electrical &amp; Computer Engr
    ## 1882                            Physics
    ## 1883 Human Development&amp;Family Study
    ## 1884                         Law School
    ## 1885               Risk &amp; Insurance
    ## 1886                         Statistics
    ## 1887                            Finance
    ## 1888           Gender And Women Studies
    ## 1889     Ms In Biotechnology Degree Prg
    ## 1890             Biomolecular Chemistry
    ## 1891              Ex Mba Program Office
    ## 1892                  Computer Sciences
    ## 1893                              Dance
    ## 1894                         Psychology
    ## 1895      Industrial &amp; Systems Engr
    ## 1896                    Medical Physics
    ## 1897                           Pharmacy
    ## 1898   Management &amp; Human Resources
    ## 1899        Life Sciences Communication
    ## 1900                        Mathematics
    ## 1901                  Computer Sciences
    ## 1902     Orthopedics And Rehabilitation
    ## 1903        German, Nordic &amp; Slavic
    ## 1904          Language Sciences Program
    ## 1905  Biostatistics&amp;Med Informatics
    ## 1906                        Art History
    ## 1907                  Computer Sciences
    ## 1908               Medical Microbiology
    ## 1909                            Surgery
    ## 1910             Accting &amp; Info Sys
    ## 1911                          Sociology
    ## 1912     Civil &amp; Environmental Engr
    ## 1913     Asian Languages &amp; Cultures
    ## 1914                          Sociology
    ## 1915                       Biochemistry
    ## 1916                           Pharmacy
    ## 1917      Engr Professional Development
    ## 1918         Population Health Sciences
    ## 1919              Counseling Psychology
    ## 1920      Industrial &amp; Systems Engr
    ## 1921                Engineering Physics
    ## 1922                         Entomology
    ## 1923           Gender And Women Studies
    ## 1924                        Mathematics
    ## 1925           Office Of Sustainability
    ## 1926             Accting &amp; Info Sys
    ## 1927                   Academic Affairs
    ## 1928                         Geoscience
    ## 1929     Electrical &amp; Computer Engr
    ## 1930            Comparative Biosciences
    ## 1931                Theatre &amp; Drama
    ## 1932  Communication Sci &amp; Disorders
    ## 1933            School Of Human Ecology
    ## 1934                            Surgery
    ## 1935                           Medicine
    ## 1936      Industrial &amp; Systems Engr
    ## 1937                          Marketing
    ## 1938         Educational Policy Studies
    ## 1939                               #N/A
    ## 1940                 French And Italian
    ## 1941       Se Asian Summer Studies Inst
    ## 1942      Ctr For Integrated Agric Syst
    ## 1943      Cell And Regenerative Biology
    ## 1944                  Political Science
    ## 1945                           Medicine
    ## 1946                           Oncology
    ## 1947                  Surgical Sciences
    ## 1948                           Genetics
    ## 1949  Real Estate &amp; Urgan Land Econ
    ## 1950                         Statistics
    ## 1951                         Statistics
    ## 1952     Civil &amp; Environmental Engr
    ## 1953                        Kinesiology
    ## 1954 Human Development&amp;Family Study
    ## 1955                     Anesthesiology
    ## 1956  Journalism&amp;Mass Communication
    ## 1957  Operations &amp; Information Mgmt
    ## 1958                    Volunteer Staff
    ## 1959                           Pharmacy
    ## 1960                 Communication Arts
    ## 1961                 Communication Arts
    ## 1962                       Food Science
    ## 1963                            Nursing
    ## 1964            Comparative Biosciences
    ## 1965                            Nursing
    ## 1966                            Nursing
    ## 1967              Counseling Psychology
    ## 1968              Counseling Psychology
    ## 1969        German, Nordic &amp; Slavic
    ## 1970         Curriculum And Instruction
    ## 1971  Rehab Psychology &amp; Special Ed
    ## 1972                         Geoscience
    ## 1973                        Amer Ind St
    ## 1974                          Geography
    ## 1975  Biostatistics&amp;Med Informatics
    ## 1976                           Medicine
    ## 1977                    Family Medicine
    ## 1978         Educational Policy Studies
    ## 1979                       Food Science
    ## 1980                           Medicine
    ## 1981     Biological Systems Engineering
    ## 1982     Electrical &amp; Computer Engr
    ## 1983                       Anthropology
    ## 1984             Biomedical Engineering
    ## 1985      Industrial &amp; Systems Engr
    ## 1986               Grainger Ctr For Scm
    ## 1987                        Mathematics
    ## 1988                  Surgical Sciences
    ## 1989                         Psychology
    ## 1990      Planning &amp; Landscape Arch
    ## 1991      Forest &amp; Wildlife Ecology
    ## 1992                          Neurology
    ## 1993             Accting &amp; Info Sys
    ## 1994     Chemical &amp; Biological Engr
    ## 1995                Integrative Biology
    ## 1996     Electrical &amp; Computer Engr
    ## 1997     Electrical &amp; Computer Engr
    ## 1998              Counseling Psychology
    ## 1999          Language Sciences Program
    ## 2000                         Psychology
    ## 2001                                Art
    ## 2002                    Plant Pathology
    ## 2003         Curriculum And Instruction
    ## 2004     Ms In Biotechnology Degree Prg
    ## 2005                           Is Major
    ## 2006                         Philosophy
    ## 2007                              Dance
    ## 2008                         Law School
    ## 2009             General Administration
    ## 2010           African Cultural Studies
    ## 2011                             Botany
    ## 2012                           Pharmacy
    ## 2013                          Neurology
    ## 2014                          Economics
    ## 2015                        Social Work
    ## 2016     Civil Society And Comm Studies
    ## 2017  Ed Leadership&amp;Policy Analysis
    ## 2018      Cell And Regenerative Biology
    ## 2019                         Law School
    ## 2020                       Bacteriology
    ## 2021                           Oncology
    ## 2022                           Medicine
    ## 2023              Counseling Psychology
    ## 2024         Population Health Sciences
    ## 2025                        Mathematics
    ## 2026     Electrical &amp; Computer Engr
    ## 2027         Curriculum And Instruction
    ## 2028              Ft Mba Program Office
    ## 2029       Wisconsin School Of Business
    ## 2030               Medical Microbiology
    ## 2031        German, Nordic &amp; Slavic
    ## 2032  Communication Sci &amp; Disorders
    ## 2033      Industrial &amp; Systems Engr
    ## 2034                  Surgical Sciences
    ## 2035  Biostatistics&amp;Med Informatics
    ## 2036           African Cultural Studies
    ## 2037     Chemical &amp; Biological Engr
    ## 2038                          Astronomy
    ## 2039                         Geoscience
    ## 2040      Planning &amp; Landscape Arch
    ## 2041                 Communication Arts
    ## 2042  Ophthalmology&amp;Visual Sciences
    ## 2043                           Pharmacy
    ## 2044                        Mathematics
    ## 2045                          Geography
    ## 2046             Educational Psychology
    ## 2047                   Medical Sciences
    ## 2048                           Pharmacy
    ## 2049                         Psychology
    ## 2050 Atmospheric &amp; Oceanic Sciences
    ## 2051                   Medical Sciences
    ## 2052                  Political Science
    ## 2053                            Finance
    ## 2054                         Entomology
    ## 2055                        Art History
    ## 2056       Wisconsin School Of Business
    ## 2057                        Mathematics
    ## 2058                          Chemistry
    ## 2059                        Art History
    ## 2060                           Pharmacy
    ## 2061                   Student Services
    ## 2062     Ms In Biotechnology Degree Prg
    ## 2063              Counseling Psychology
    ## 2064 Atmospheric &amp; Oceanic Sciences
    ## 2065                Integrative Biology
    ## 2066                  Political Science
    ## 2067                       Biochemistry
    ## 2068     Electrical &amp; Computer Engr
    ## 2069                   Medical Sciences
    ## 2070         Bolz Center For Arts Admin
    ## 2071           Pathobiological Sciences
    ## 2072                        Kinesiology
    ## 2073                          Geography
    ## 2074                         Philosophy
    ## 2075                          Sociology
    ## 2076                           Genetics
    ## 2077             Biomedical Engineering
    ## 2078                                Art
    ## 2079                          Astronomy
    ## 2080             Accting &amp; Info Sys
    ## 2081             Educational Psychology
    ## 2082                        Social Work
    ## 2083              Counseling Psychology
    ## 2084                Integrative Biology
    ## 2085                      Naval Science
    ## 2086                                Art
    ## 2087     Chemical &amp; Biological Engr
    ## 2088     Electrical &amp; Computer Engr
    ## 2089                        Mathematics
    ## 2090                  Political Science
    ## 2091           Law, Society And Justice
    ## 2092             Accting &amp; Info Sys
    ## 2093                          Sociology
    ## 2094                  Surgical Sciences
    ## 2095                            Physics
    ## 2096                          Chemistry
    ## 2097                 Information School
    ## 2098  Journalism&amp;Mass Communication
    ## 2099                              Dance
    ## 2100      Planning &amp; Landscape Arch
    ## 2101                            English
    ## 2102                         Law School
    ## 2103     Lafollette Sch Of Publ Affairs
    ## 2104       Office Of Undergrad Advising
    ## 2105                    Volunteer Staff
    ## 2106             Biomedical Engineering
    ## 2107  Operations &amp; Information Mgmt
    ## 2108                      Africa Center
    ## 2109                            History
    ## 2110                      Asian Studies
    ## 2111                           Medicine
    ## 2112                         Pediatrics
    ## 2113                             Botany
    ## 2114        Mead Witter School Of Music
    ## 2115                        Kinesiology
    ## 2116                         Law School
    ## 2117                            Physics
    ## 2118                            History
    ## 2119  Ed Leadership&amp;Policy Analysis
    ## 2120         Curriculum And Instruction
    ## 2121     Ms In Biotechnology Degree Prg
    ## 2122  Ophthalmology&amp;Visual Sciences
    ## 2123                       Anthropology
    ## 2124  Journalism&amp;Mass Communication
    ## 2125      Engr Professional Development
    ## 2126                            Nursing
    ## 2127            School Of Human Ecology
    ## 2128                          Economics
    ## 2129  Classic &amp; Ancient Near E Stds
    ## 2130         Curriculum And Instruction
    ## 2131                 Communication Arts
    ## 2132                           Medicine
    ## 2133                  Surgical Sciences
    ## 2134                     Administration
    ## 2135     Civil &amp; Environmental Engr
    ## 2136                          Chemistry
    ## 2137           Gender And Women Studies
    ## 2138                          Radiology
    ## 2139                            Nursing
    ## 2140                         Law School
    ## 2141                           Medicine
    ## 2142  Ed Leadership&amp;Policy Analysis
    ## 2143  Ed Leadership&amp;Policy Analysis
    ## 2144                           Medicine
    ## 2145                           Pharmacy
    ## 2146             Spanish And Portuguese
    ## 2147                  Academic Programs
    ## 2148               Neurological Surgery
    ## 2149               Medical Microbiology
    ## 2150                        Social Work
    ## 2151        Life Sciences Communication
    ## 2152                          Geography
    ## 2153                            Finance
    ## 2154        German, Nordic &amp; Slavic
    ## 2155  Biostatistics&amp;Med Informatics
    ## 2156                         Statistics
    ## 2157                 French And Italian
    ## 2158           Gender And Women Studies
    ## 2159             Spanish And Portuguese
    ## 2160                        Mathematics
    ## 2161                           Medicine
    ## 2162                           Oncology
    ## 2163                         Philosophy
    ## 2164                        Social Work
    ## 2165   Management &amp; Human Resources
    ## 2166                        Social Work
    ## 2167                        Mathematics
    ## 2168             Educational Psychology
    ## 2169                       Biochemistry
    ## 2170                    Medical Physics
    ## 2171                     Design Studies
    ## 2172                           Pharmacy
    ## 2173                         Geoscience
    ## 2174                         Law School
    ## 2175              Cals Academic Affairs
    ## 2176     Lafollette Sch Of Publ Affairs
    ## 2177                            History
    ## 2178      Industrial &amp; Systems Engr
    ## 2179                 Bba Program Office
    ## 2180                  Academic Programs
    ## 2181        German, Nordic &amp; Slavic
    ## 2182        German, Nordic &amp; Slavic
    ## 2183                 French And Italian
    ## 2184             Mechanical Engineering
    ## 2185     Electrical &amp; Computer Engr
    ## 2186                          Chemistry
    ## 2187     Electrical &amp; Computer Engr
    ## 2188          Animal And Dairy Sciences
    ## 2189                  Computer Sciences
    ## 2190                                Art
    ## 2191                        Social Work
    ## 2192             Mechanical Engineering
    ## 2193     Chemical &amp; Biological Engr
    ## 2194      Engr Professional Development
    ## 2195                        Mathematics
    ## 2196                  Academic Programs
    ## 2197                  Surgical Sciences
    ## 2198  Ed Leadership&amp;Policy Analysis
    ## 2199                Theatre &amp; Drama
    ## 2200     Lafollette Sch Of Publ Affairs
    ## 2201             Mechanical Engineering
    ## 2202                 Communication Arts
    ## 2203                    Family Medicine
    ## 2204      Industrial &amp; Systems Engr
    ## 2205                          Geography
    ## 2206     Asian Languages &amp; Cultures
    ## 2207                         Law School
    ## 2208             Educational Psychology
    ## 2209                         Law School
    ## 2210                           Medicine
    ## 2211                         Law School
    ## 2212                                Art
    ## 2213 Agricultural&amp;Applied Economics
    ## 2214                 Information School
    ## 2215                            History
    ## 2216                           Oncology
    ## 2217                      Asian Amer St
    ## 2218      Forest &amp; Wildlife Ecology
    ## 2219                  Political Science
    ## 2220        German, Nordic &amp; Slavic
    ## 2221         Educational Policy Studies
    ## 2222                           Medicine
    ## 2223                            Physics
    ## 2224                         Pediatrics
    ## 2225        Mead Witter School Of Music
    ## 2226  Rehab Psychology &amp; Special Ed
    ## 2227                          Economics
    ## 2228                   Medical Sciences
    ## 2229                Integrative Biology
    ## 2230                         Law School
    ## 2231                            English
    ## 2232             Accting &amp; Info Sys
    ## 2233                            Nursing
    ## 2234 Atmospheric &amp; Oceanic Sciences
    ## 2235         Department Of Neuroscience
    ## 2236                        Social Work
    ## 2237                          Geography
    ## 2238      Planning &amp; Landscape Arch
    ## 2239                          Marketing
    ## 2240                  Surgical Sciences
    ## 2241      Planning &amp; Landscape Arch
    ## 2242                         Pediatrics
    ## 2243                            Surgery
    ## 2244  Materials Science&amp;Engineering
    ## 2245 Atmospheric &amp; Oceanic Sciences
    ## 2246     Asian Languages &amp; Cultures
    ## 2247                         Law School
    ## 2248                 Communication Arts
    ## 2249  Ed Leadership&amp;Policy Analysis
    ## 2250                     Human Oncology
    ## 2251              Afro-American Studies
    ## 2252     Electrical &amp; Computer Engr
    ## 2253                     Human Oncology
    ## 2254                        Social Work
    ## 2255             Biomolecular Chemistry
    ## 2256            School Of Human Ecology
    ## 2257                           Pharmacy
    ## 2258           African Cultural Studies
    ## 2259                            History
    ## 2260                  Surgical Sciences
    ## 2261                            Nursing
    ## 2262  Rehab Psychology &amp; Special Ed
    ## 2263  Communication Sci &amp; Disorders
    ## 2264                  Surgical Sciences
    ## 2265               Risk &amp; Insurance
    ## 2266 Agricultural&amp;Applied Economics
    ## 2267                          Economics
    ## 2268         Population Health Sciences
    ## 2269        Mead Witter School Of Music
    ## 2270 Liberal Arts &amp; Applied Studies
    ## 2271                            English
    ## 2272                            Physics
    ## 2273                          Economics
    ## 2274                  Surgical Sciences
    ## 2275           Law, Society And Justice
    ## 2276         Curriculum And Instruction
    ## 2277                Engineering Physics
    ## 2278      Engr Professional Development
    ## 2279     Chemical &amp; Biological Engr
    ## 2280             Biomedical Engineering
    ## 2281                        Social Work
    ## 2282                   Consumer Science
    ## 2283                            History
    ## 2284           African Cultural Studies
    ## 2285                  Computer Sciences
    ## 2286             Lat Amer Carib Iber St
    ## 2287      Planning &amp; Landscape Arch
    ## 2288         Population Health Sciences
    ## 2289     Ctr For Rus East Eur Cent Asia
    ## 2290                         Psychiatry
    ## 2291      Forest &amp; Wildlife Ecology
    ## 2292                         Pediatrics
    ## 2293                         Philosophy
    ## 2294      Engr Professional Development
    ## 2295                            Urology
    ## 2296     Asian Languages &amp; Cultures
    ## 2297                       Religious St
    ## 2298                         Geoscience
    ## 2299                                Art
    ## 2300             Educational Psychology
    ## 2301                          Chemistry
    ## 2302                          Geography
    ## 2303                         Pediatrics
    ## 2304              Counseling Psychology
    ## 2305     Ctr For Rus East Eur Cent Asia
    ## 2306                        Social Work
    ## 2307             Mechanical Engineering
    ## 2308             Mechanical Engineering
    ## 2309              Academic Partnerships
    ## 2310  Classic &amp; Ancient Near E Stds
    ## 2311         Educational Policy Studies
    ## 2312  Ed Leadership&amp;Policy Analysis
    ## 2313        Mead Witter School Of Music
    ## 2314     Lafollette Sch Of Publ Affairs
    ## 2315                    Family Medicine
    ## 2316        Life Sciences Communication
    ## 2317     Biological Systems Engineering
    ## 2318                        Art History
    ## 2319     Civil &amp; Environmental Engr
    ## 2320  Dept Of Med History&amp;Bioethics
    ## 2321           Gender And Women Studies
    ## 2322   Management &amp; Human Resources
    ## 2323     Lafollette Sch Of Publ Affairs
    ## 2324                       Anthropology
    ## 2325                            English
    ## 2326                           Medicine
    ## 2327                            Nursing
    ## 2328  Ophthalmology&amp;Visual Sciences
    ## 2329             Spanish And Portuguese
    ## 2330                            History
    ## 2331                          Marketing
    ## 2332                   Medical Sciences
    ## 2333        Life Sciences Communication
    ## 2334                Integrative Biology
    ## 2335                            Nursing
    ## 2336  Biostatistics&amp;Med Informatics
    ## 2337               Nutritional Sciences
    ## 2338                            English
    ## 2339                        Social Work
    ## 2340                  Computer Sciences
    ## 2341                            English
    ## 2342                 Information School
    ## 2343                   Medical Sciences
    ## 2344         Curriculum And Instruction
    ## 2345  Ophthalmology&amp;Visual Sciences
    ## 2346              Counseling Psychology
    ## 2347                         Psychology
    ## 2348                       Horticulture
    ## 2349                         Law School
    ## 2350                Engineering Physics
    ## 2351             Biomedical Engineering
    ## 2352                           Is Major
    ## 2353            School Of Human Ecology
    ## 2354  Communication Sci &amp; Disorders
    ## 2355                          Sociology
    ## 2356     Civil &amp; Environmental Engr
    ## 2357                            Nursing
    ## 2358                       Religious St
    ## 2359                            English
    ## 2360                            Nursing
    ## 2361                Engineering Physics
    ## 2362     Electrical &amp; Computer Engr
    ## 2363     Civil &amp; Environmental Engr
    ## 2364                       Biochemistry
    ## 2365                            English
    ## 2366                            History
    ## 2367                   Consumer Science
    ## 2368                Integrative Biology
    ## 2369             Mechanical Engineering
    ## 2370                            Nursing
    ## 2371             Mechanical Engineering
    ## 2372             Accting &amp; Info Sys
    ## 2373                            Nursing
    ## 2374  Ed Leadership&amp;Policy Analysis
    ## 2375                         Pediatrics
    ## 2376                           Medicine
    ## 2377  Pathology&amp;Laboratory Medicine
    ## 2378  Pathology&amp;Laboratory Medicine
    ## 2379                       Bacteriology
    ## 2380 Atmospheric &amp; Oceanic Sciences
    ## 2381                            Surgery
    ## 2382        Mead Witter School Of Music
    ## 2383                   Medical Sciences
    ## 2384     Electrical &amp; Computer Engr
    ## 2385                          Marketing
    ## 2386                          Sociology
    ## 2387                 Information School
    ## 2388      Planning &amp; Landscape Arch
    ## 2389                         Law School
    ## 2390                           Medicine
    ## 2391                         Law School
    ## 2392                          Geography
    ## 2393                         Law School
    ## 2394     Civil &amp; Environmental Engr
    ## 2395                   Consumer Science
    ## 2396                          Sociology
    ## 2397         Population Health Sciences
    ## 2398                   Medical Sciences
    ## 2399                   Academic Affairs
    ## 2400                            English
    ## 2401                    Volunteer Staff
    ## 2402                        Social Work
    ## 2403         Curriculum And Instruction
    ## 2404              Cals Academic Affairs
    ## 2405            Weinert Center For Entr
    ## 2406                            Physics
    ## 2407        Obstetrics &amp; Gynecology
    ## 2408                       Horticulture
    ## 2409                            Finance
    ## 2410                            Surgery
    ## 2411          Animal And Dairy Sciences
    ## 2412                         Law School
    ## 2413                Integrative Biology
    ## 2414                            English
    ## 2415  Communication Sci &amp; Disorders
    ## 2416           Pathobiological Sciences
    ## 2417        German, Nordic &amp; Slavic
    ## 2418                         Law School
    ## 2419             Mechanical Engineering
    ## 2420                             Botany
    ## 2421                            Nursing
    ## 2422      Engr Professional Development
    ## 2423                         Pediatrics
    ## 2424                            Nursing
    ## 2425         Population Health Sciences
    ## 2426  Operations &amp; Information Mgmt
    ## 2427         Curriculum And Instruction
    ## 2428                  Political Science
    ## 2429  Ed Leadership&amp;Policy Analysis
    ## 2430      Forest &amp; Wildlife Ecology
    ## 2431                          Economics
    ## 2432                        Social Work
    ## 2433         Curriculum And Instruction
    ## 2434                                Art
    ## 2435  Biostatistics&amp;Med Informatics
    ## 2436                        Social Work
    ## 2437                       Biochemistry
    ## 2438                            Finance
    ## 2439       Grainger Institute For Engr.
    ## 2440     Chemical &amp; Biological Engr
    ## 2441                            Physics
    ## 2442                       Biochemistry
    ## 2443                                Art
    ## 2444  Journalism&amp;Mass Communication
    ## 2445                            Finance
    ## 2446                 Information School
    ## 2447                       Horticulture
    ## 2448             Mechanical Engineering
    ## 2449                   Medical Sciences
    ## 2450     Biological Systems Engineering
    ## 2451                            Physics
    ## 2452                 Communication Arts
    ## 2453  Classic &amp; Ancient Near E Stds
    ## 2454                   Military Science
    ## 2455                           Medicine
    ## 2456     Electrical &amp; Computer Engr
    ## 2457               Biotechnology Center
    ## 2458            School Of Human Ecology
    ## 2459                          Sociology
    ## 2460                    Family Medicine
    ## 2461  Operations &amp; Information Mgmt
    ## 2462     Civil &amp; Environmental Engr
    ## 2463 Agricultural&amp;Applied Economics
    ## 2464                            Physics
    ## 2465                       Food Science
    ## 2466               Nutritional Sciences
    ## 2467     Civil &amp; Environmental Engr
    ## 2468  Communication Sci &amp; Disorders
    ## 2469          Animal And Dairy Sciences
    ## 2470                         Entomology
    ## 2471        Obstetrics &amp; Gynecology
    ## 2472                           Pharmacy
    ## 2473                  Computer Sciences
    ## 2474                         Statistics
    ## 2475        Mead Witter School Of Music
    ## 2476                         Pediatrics
    ## 2477                        Kinesiology
    ## 2478                  Academic Programs
    ## 2479                        Mathematics
    ## 2480                          Economics
    ## 2481  Ed Leadership&amp;Policy Analysis
    ## 2482      Forest &amp; Wildlife Ecology
    ## 2483      Planning &amp; Landscape Arch
    ## 2484                       Bacteriology
    ## 2485                            Nursing
    ## 2486                            Nursing
    ## 2487                           Genetics
    ## 2488                          Chemistry
    ## 2489                     Anesthesiology
    ## 2490                        Social Work
    ## 2491                            Nursing
    ## 2492                Air Force Aerospace
    ## 2493                          Marketing
    ## 2494                       Soil Science
    ## 2495                          Sociology
    ## 2496                         Pediatrics
    ## 2497  Ed Leadership&amp;Policy Analysis
    ## 2498                   Medical Sciences
    ## 2499      Forest &amp; Wildlife Ecology
    ## 2500                           Medicine
    ## 2501                           Genetics
    ## 2502             Spanish And Portuguese
    ## 2503             Accting &amp; Info Sys
    ## 2504                   Medical Sciences
    ## 2505          Animal And Dairy Sciences
    ## 2506                         Law School
    ## 2507  Communication Sci &amp; Disorders
    ## 2508                       Biochemistry
    ## 2509         Population Health Sciences
    ## 2510                           Medicine
    ## 2511  Materials Science&amp;Engineering
    ## 2512                            English
    ## 2513                           Genetics
    ## 2514        Mead Witter School Of Music
    ## 2515  Communication Sci &amp; Disorders
    ## 2516              Counseling Psychology
    ## 2517               Risk &amp; Insurance
    ## 2518  Pathology&amp;Laboratory Medicine
    ## 2519                           Pharmacy
    ## 2520                         Geoscience
    ## 2521                         Pediatrics
    ## 2522                         Law School
    ## 2523                                Art
    ## 2524                Theatre &amp; Drama
    ## 2525 Atmospheric &amp; Oceanic Sciences
    ## 2526                         Pediatrics
    ## 2527 Atmospheric &amp; Oceanic Sciences
    ## 2528                  Political Science
    ## 2529            Biology Core Curriculum
    ## 2530             Mechanical Engineering
    ## 2531     Chemical &amp; Biological Engr
    ## 2532                         Psychology
    ## 2533             Mechanical Engineering
    ## 2534 Agricultural&amp;Applied Economics
    ## 2535              Counseling Psychology
    ## 2536           Gender And Women Studies
    ## 2537                    Volunteer Staff
    ## 2538                        Art History
    ## 2539                         Law School
    ## 2540                 French And Italian
    ## 2541                           Agronomy
    ## 2542                   Medical Sciences
    ## 2543                       Anthropology
    ## 2544                            Finance
    ## 2545                        Kinesiology
    ## 2546      Forest &amp; Wildlife Ecology
    ## 2547  Journalism&amp;Mass Communication
    ## 2548 Atmospheric &amp; Oceanic Sciences
    ## 2549                         Law School
    ## 2550                       Biochemistry
    ## 2551                          Sociology
    ## 2552         Population Health Sciences
    ## 2553  Biostatistics&amp;Med Informatics
    ## 2554                                Art
    ## 2555     Civil &amp; Environmental Engr
    ## 2556                            Nursing
    ## 2557           Pathobiological Sciences
    ## 2558  Real Estate &amp; Urgan Land Econ
    ## 2559                        Social Work
    ## 2560             Information Technology
    ## 2561                         Psychiatry
    ## 2562                            Finance
    ## 2563                            English
    ## 2564                            History
    ## 2565      Engr Professional Development
    ## 2566                         Law School
    ## 2567            School Of Human Ecology
    ## 2568                                Art
    ## 2569                            Nursing
    ## 2570                         Psychology
    ## 2571                          Marketing
    ## 2572                        Mathematics
    ## 2573        Mead Witter School Of Music
    ## 2574      Cell And Regenerative Biology
    ## 2575            School Of Human Ecology
    ## 2576                           Genetics
    ## 2577                            Surgery
    ## 2578         Curriculum And Instruction
    ## 2579         Department Of Neuroscience
    ## 2580                           Pharmacy
    ## 2581                          Economics
    ## 2582                           Pharmacy
    ## 2583   Management &amp; Human Resources
    ## 2584         Educational Policy Studies
    ## 2585                         Psychology
    ## 2586  Ophthalmology&amp;Visual Sciences
    ## 2587     Civil &amp; Environmental Engr
    ## 2588                            English
    ## 2589                   Medical Sciences
    ## 2590                  Political Science
    ## 2591                         Law School
    ## 2592                   Medical Sciences
    ## 2593     Civil &amp; Environmental Engr
    ## 2594                          Radiology
    ## 2595                 Communication Arts
    ## 2596                   Academic Affairs
    ## 2597      Forest &amp; Wildlife Ecology
    ## 2598      Engr Professional Development
    ## 2599                        Social Work
    ## 2600      Engr Professional Development
    ## 2601                             Botany
    ## 2602                   Medical Sciences
    ## 2603                           Genetics
    ## 2604                       Biochemistry
    ## 2605 Agricultural&amp;Applied Economics
    ## 2606                        Art History
    ## 2607                                Art
    ## 2608             Biomedical Engineering
    ## 2609             Biomedical Engineering
    ## 2610                           Medicine
    ## 2611     Civil &amp; Environmental Engr
    ## 2612             Spanish And Portuguese
    ## 2613                 Emergency Medicine
    ## 2614                           Medicine
    ## 2615                    Plant Pathology
    ## 2616                        Kinesiology
    ## 2617             Educational Psychology
    ## 2618        Mead Witter School Of Music
    ## 2619                            English
    ## 2620             Educational Psychology
    ## 2621                           Pharmacy
    ## 2622             Mechanical Engineering
    ## 2623     Civil &amp; Environmental Engr
    ## 2624     Civil &amp; Environmental Engr
    ## 2625                    Family Medicine
    ## 2626        Mead Witter School Of Music
    ## 2627              Counseling Psychology
    ## 2628                         Geoscience
    ## 2629  Communication Sci &amp; Disorders
    ## 2630                          Economics
    ## 2631              Counseling Psychology
    ## 2632                            Finance
    ## 2633                         Law School
    ## 2634  Real Estate &amp; Urgan Land Econ
    ## 2635                   Medical Sciences
    ## 2636             Educational Psychology
    ## 2637      Forest &amp; Wildlife Ecology
    ## 2638      Industrial &amp; Systems Engr
    ## 2639     Engineering Student Developmnt
    ## 2640           Pathobiological Sciences
    ## 2641  Pathology&amp;Laboratory Medicine
    ## 2642     Ctr For Rus East Eur Cent Asia
    ## 2643                            English
    ## 2644            School Of Human Ecology
    ## 2645                    Plant Pathology
    ## 2646                         Pediatrics
    ## 2647                       Biochemistry
    ## 2648     Electrical &amp; Computer Engr
    ## 2649         Curriculum And Instruction
    ## 2650                            History
    ## 2651              Counseling Psychology
    ## 2652                    Family Medicine
    ## 2653                              Dance
    ## 2654     Civil &amp; Environmental Engr
    ## 2655        South Asian Sum Lang Instit
    ## 2656                    Medical Physics
    ## 2657  Pathology&amp;Laboratory Medicine
    ## 2658     Lafollette Sch Of Publ Affairs
    ## 2659                       Food Science
    ## 2660                            English
    ## 2661             Spanish And Portuguese
    ## 2662                         Statistics
    ## 2663                         Statistics
    ## 2664                  Surgical Sciences
    ## 2665                            History
    ## 2666                             Botany
    ## 2667             Educational Psychology
    ## 2668                           Medicine
    ## 2669                       Biochemistry
    ## 2670                         Psychiatry
    ## 2671                            Physics
    ## 2672                            Physics
    ## 2673          Animal And Dairy Sciences
    ## 2674              Counseling Psychology
    ## 2675                          Chemistry
    ## 2676                        Amer Ind St
    ## 2677                            Surgery
    ## 2678     Chemical &amp; Biological Engr
    ## 2679          Animal And Dairy Sciences
    ## 2680                          Radiology
    ## 2681         Educational Policy Studies
    ## 2682                Theatre &amp; Drama
    ## 2683             Mechanical Engineering
    ## 2684     Biological Systems Engineering
    ## 2685                            Nursing
    ## 2686                         Psychology
    ## 2687                         Pediatrics
    ## 2688                  Computer Sciences
    ## 2689                              Dance
    ## 2690         Population Health Sciences
    ## 2691                        Mathematics
    ## 2692     Civil &amp; Environmental Engr
    ## 2693                  Computer Sciences
    ## 2694                  Political Science
    ## 2695                           Agronomy
    ## 2696                  Computer Sciences
    ## 2697               Neurological Surgery
    ## 2698                       Bacteriology
    ## 2699           Pathobiological Sciences
    ## 2700        German, Nordic &amp; Slavic
    ## 2701           Pathobiological Sciences
    ## 2702                 Information School
    ## 2703  Materials Science&amp;Engineering
    ## 2704                         Pediatrics
    ## 2705                           Medicine
    ## 2706        Mead Witter School Of Music
    ## 2707                                Art
    ## 2708          Animal And Dairy Sciences
    ## 2709         Bolz Center For Arts Admin
    ## 2710                           Pharmacy
    ## 2711                         Law School
    ## 2712                          Economics
    ## 2713          Animal And Dairy Sciences
    ## 2714                            Urology
    ## 2715      Forest &amp; Wildlife Ecology
    ## 2716  Real Estate &amp; Urgan Land Econ
    ## 2717  Journalism&amp;Mass Communication
    ## 2718                 Information School
    ## 2719     Asian Languages &amp; Cultures
    ## 2720                       Religious St
    ## 2721                       Biochemistry
    ## 2722                  Surgical Sciences
    ## 2723                   Academic Affairs
    ## 2724                    Family Medicine
    ## 2725                  Political Science
    ## 2726                                Art
    ## 2727                    Volunteer Staff
    ## 2728  Community &amp; Environ Sociology
    ## 2729                    Plant Pathology
    ## 2730      Forest &amp; Wildlife Ecology
    ## 2731                Integrative Biology
    ## 2732     Electrical &amp; Computer Engr
    ## 2733                            Finance
    ## 2734            School Of Human Ecology
    ## 2735                  Academic Programs
    ## 2736                        Social Work
    ## 2737                   Medical Sciences
    ## 2738                            History
    ## 2739                            Nursing
    ## 2740                          Wiscience
    ## 2741         Department Of Neuroscience
    ## 2742                          Geography
    ## 2743      Industrial &amp; Systems Engr
    ## 2744  Journalism&amp;Mass Communication
    ## 2745                        Mathematics
    ## 2746                            History
    ## 2747                         Pediatrics
    ## 2748                       Religious St
    ## 2749                         Geoscience
    ## 2750                   Academic Affairs
    ## 2751         Educational Policy Studies
    ## 2752                        Mathematics
    ## 2753             Spanish And Portuguese
    ## 2754             Mechanical Engineering
    ## 2755             Biomedical Engineering
    ## 2756                          Sociology
    ## 2757         Curriculum And Instruction
    ## 2758                         Psychology
    ## 2759                         Statistics
    ## 2760  Journalism&amp;Mass Communication
    ## 2761             Mechanical Engineering
    ## 2762                       Bacteriology
    ## 2763         Curriculum And Instruction
    ## 2764              Counseling Psychology
    ## 2765     Electrical &amp; Computer Engr
    ## 2766                       Biochemistry
    ## 2767                            Nursing
    ## 2768                  Computer Sciences
    ## 2769                       Bacteriology
    ## 2770        Mead Witter School Of Music
    ## 2771          Animal And Dairy Sciences
    ## 2772                            Surgery
    ## 2773                        Mathematics
    ## 2774         Department Of Neuroscience
    ## 2775        German, Nordic &amp; Slavic
    ## 2776     Chemical &amp; Biological Engr
    ## 2777                        Social Work
    ## 2778          Animal And Dairy Sciences
    ## 2779                 Information School
    ## 2780                    Medical Physics
    ## 2781                           Pharmacy
    ## 2782  Pathology&amp;Laboratory Medicine
    ## 2783                           Pharmacy
    ## 2784         Department Of Neuroscience
    ## 2785                                Art
    ## 2786               Risk &amp; Insurance
    ## 2787                  Ctr For Jewish St
    ## 2788     Ctr For Relig&amp;Global Citiz
    ## 2789                         Psychiatry
    ## 2790  Rehab Psychology &amp; Special Ed
    ## 2791                Integrative Biology
    ## 2792                           Oncology
    ## 2793                          Economics
    ## 2794     Orthopedics And Rehabilitation
    ## 2795                          Geography
    ## 2796             Mechanical Engineering
    ## 2797        Mead Witter School Of Music
    ## 2798                           Pharmacy
    ## 2799                    Plant Pathology
    ## 2800 Atmospheric &amp; Oceanic Sciences
    ## 2801        Mead Witter School Of Music
    ## 2802                        Social Work
    ## 2803  Biostatistics&amp;Med Informatics
    ## 2804           African Cultural Studies
    ## 2805                       Soil Science
    ## 2806                 Information School
    ## 2807                                Art
    ## 2808                        Social Work
    ## 2809         Curriculum And Instruction
    ## 2810             Mechanical Engineering
    ## 2811             Mechanical Engineering
    ## 2812      Ctr Study Upper Midwest Cultr
    ## 2813                          Economics
    ## 2814                           Medicine
    ## 2815                 French And Italian
    ## 2816     Biological Systems Engineering
    ## 2817  Rehab Psychology &amp; Special Ed
    ## 2818         Curriculum And Instruction
    ## 2819     Civil &amp; Environmental Engr
    ## 2820                              Dance
    ## 2821              Counseling Psychology
    ## 2822 Agricultural&amp;Applied Economics
    ## 2823                         Psychology
    ## 2824                   Medical Sciences
    ## 2825                            Physics
    ## 2826                         Psychology
    ## 2827  Materials Science&amp;Engineering
    ## 2828              Inst Reg Intl Studies
    ## 2829                           Medicine
    ## 2830                            Physics
    ## 2831                         Psychology
    ## 2832                  Surgical Sciences
    ## 2833                     Design Studies
    ## 2834             Biomedical Engineering
    ## 2835                  Computer Sciences
    ## 2836                            Nursing
    ## 2837  Pathology&amp;Laboratory Medicine
    ## 2838           Pathobiological Sciences
    ## 2839          Language Sciences Program
    ## 2840                 Information School
    ## 2841  Ed Leadership&amp;Policy Analysis
    ## 2842            Comparative Biosciences
    ## 2843         Population Health Sciences
    ## 2844                  Surgical Sciences
    ## 2845             Spanish And Portuguese
    ## 2846                           Medicine
    ## 2847             Mechanical Engineering
    ## 2848           Pathobiological Sciences
    ## 2849                            Finance
    ## 2850             Biomedical Engineering
    ## 2851  Pathology&amp;Laboratory Medicine
    ## 2852              Cals Academic Affairs
    ## 2853                  Computer Sciences
    ## 2854                         Statistics
    ## 2855     Electrical &amp; Computer Engr
    ## 2856        Mead Witter School Of Music
    ## 2857     Civil &amp; Environmental Engr
    ## 2858             Spanish And Portuguese
    ## 2859   Management &amp; Human Resources
    ## 2860                            Physics
    ## 2861     Electrical &amp; Computer Engr
    ## 2862            School Of Human Ecology
    ## 2863            School Of Human Ecology
    ## 2864              Counseling Psychology
    ## 2865               Medical Microbiology
    ## 2866                   Medical Sciences
    ## 2867                            English
    ## 2868                    Animal Sciences
    ## 2869                  Surgical Sciences
    ## 2870           Gender And Women Studies
    ## 2871                            Nursing
    ## 2872                         Law School
    ## 2873                            Nursing
    ## 2874                            Nursing
    ## 2875     Civil &amp; Environmental Engr
    ## 2876                         Psychiatry
    ## 2877 Agricultural&amp;Applied Economics
    ## 2878                         Philosophy
    ## 2879                          Geography
    ## 2880                                Art
    ## 2881                           Pharmacy
    ## 2882        Life Sciences Communication
    ## 2883                        Dermatology
    ## 2884      Engr Professional Development
    ## 2885                         Psychology
    ## 2886           Pathobiological Sciences
    ## 2887                          Chemistry
    ## 2888                            Physics
    ## 2889                 Emergency Medicine
    ## 2890        German, Nordic &amp; Slavic
    ## 2891 Agricultural&amp;Applied Economics
    ## 2892     Lafollette Sch Of Publ Affairs
    ## 2893               Risk &amp; Insurance
    ## 2894                        Social Work
    ## 2895     Lafollette Sch Of Publ Affairs
    ## 2896                           Pharmacy
    ## 2897                Engineering Physics
    ## 2898  Classic &amp; Ancient Near E Stds
    ## 2899                  Academic Programs
    ## 2900                            Surgery
    ## 2901  Communication Sci &amp; Disorders
    ## 2902                         Law School
    ## 2903                          Chemistry
    ## 2904             Educational Psychology
    ## 2905              Counseling Psychology
    ## 2906                         Entomology
    ## 2907                        Kinesiology
    ## 2908     Chemical &amp; Biological Engr
    ## 2909                           Genetics
    ## 2910                  Surgical Sciences
    ## 2911                            Finance
    ## 2912                       Anthropology
    ## 2913                        Social Work
    ## 2914                   Academic Affairs
    ## 2915      Planning &amp; Landscape Arch
    ## 2916               Nutritional Sciences
    ## 2917                Air Force Aerospace
    ## 2918        German, Nordic &amp; Slavic
    ## 2919                        Social Work
    ## 2920                  Academic Programs
    ## 2921                 Communication Arts
    ## 2922       Administration-Dean'S Office
    ## 2923                   Medical Sciences
    ## 2924                         Law School
    ## 2925                          Sociology
    ## 2926                         Law School
    ## 2927                          Chemistry
    ## 2928                            Nursing
    ## 2929                        Kinesiology
    ## 2930  Real Estate &amp; Urgan Land Econ
    ## 2931                            Surgery
    ## 2932                  Political Science
    ## 2933                  Academic Programs
    ## 2934                  Political Science
    ## 2935         Curriculum And Instruction
    ## 2936        Mead Witter School Of Music
    ## 2937  Journalism&amp;Mass Communication
    ## 2938                         Pediatrics
    ## 2939                         Law School
    ## 2940                        Mathematics
    ## 2941        Life Sciences Communication
    ## 2942     Ms In Biotechnology Degree Prg
    ## 2943              Counseling Psychology
    ## 2944                           Medicine
    ## 2945  Communication Sci &amp; Disorders
    ## 2946                         Psychology
    ## 2947                          Sociology
    ## 2948                         Law School
    ## 2949                            Nursing
    ## 2950                            Nursing
    ## 2951                         Pediatrics
    ## 2952                          Chemistry
    ## 2953                 Information School
    ## 2954             Mechanical Engineering
    ## 2955                       Biochemistry
    ## 2956                            Finance
    ## 2957                        Mathematics
    ## 2958                           Pharmacy
    ## 2959                          Economics
    ## 2960   Management &amp; Human Resources
    ## 2961                           Medicine
    ## 2962                        Dermatology
    ## 2963     Electrical &amp; Computer Engr
    ## 2964         Population Health Sciences
    ## 2965     Electrical &amp; Computer Engr
    ## 2966                              Dance
    ## 2967                           Pharmacy
    ## 2968                         Philosophy
    ## 2969             Educational Psychology
    ## 2970  Journalism&amp;Mass Communication
    ## 2971  Journalism&amp;Mass Communication
    ## 2972                 Emergency Medicine
    ## 2973           Gender And Women Studies
    ## 2974                            Finance
    ## 2975                        Mathematics
    ## 2976          Animal And Dairy Sciences
    ## 2977                            History
    ## 2978                         Statistics
    ## 2979                 Information School
    ## 2980                         Philosophy
    ## 2981      Engr Professional Development
    ## 2982             Mechanical Engineering
    ## 2983                         Law School
    ## 2984           Pathobiological Sciences
    ## 2985                Integrative Biology
    ## 2986                           Genetics
    ## 2987              Afro-American Studies
    ## 2988        Life Sciences Communication
    ## 2989           Pathobiological Sciences
    ## 2990                  Surgical Sciences
    ## 2991                        Mathematics
    ## 2992                         Law School
    ## 2993        German, Nordic &amp; Slavic
    ## 2994                           Medicine
    ## 2995                   Medical Sciences
    ## 2996             Biomolecular Chemistry
    ## 2997  Ophthalmology&amp;Visual Sciences
    ## 2998                           Medicine
    ## 2999                  Political Science
    ## 3000                        Social Work
    ## 3001                        Mathematics
    ## 3002                           Medicine
    ## 3003     Ms In Biotechnology Degree Prg
    ## 3004                     Design Studies
    ## 3005                           Oncology
    ## 3006                            English
    ## 3007        German, Nordic &amp; Slavic
    ## 3008 Agricultural&amp;Applied Economics
    ## 3009      Industrial &amp; Systems Engr
    ## 3010               Risk &amp; Insurance
    ## 3011                          Economics
    ## 3012                        Kinesiology
    ## 3013          Language Sciences Program
    ## 3014   Management &amp; Human Resources
    ## 3015            School Of Human Ecology
    ## 3016     Biological Systems Engineering
    ## 3017            School Of Human Ecology
    ## 3018                            Physics
    ## 3019                           Pharmacy
    ## 3020                            History
    ## 3021     Electrical &amp; Computer Engr
    ## 3022             Educational Psychology
    ## 3023                            English
    ## 3024                 Communication Arts
    ## 3025                           Oncology
    ## 3026  Real Estate &amp; Urgan Land Econ
    ## 3027     Chemical &amp; Biological Engr
    ## 3028     Biological Systems Engineering
    ## 3029                         Psychology
    ## 3030                          Chemistry
    ## 3031                         Law School
    ## 3032                         Philosophy
    ## 3033  Operations &amp; Information Mgmt
    ## 3034                  Computer Sciences
    ## 3035                   Consumer Science
    ## 3036      Industrial &amp; Systems Engr
    ## 3037      Planning &amp; Landscape Arch
    ## 3038              Counseling Psychology
    ## 3039                    Plant Pathology
    ## 3040                       Biochemistry
    ## 3041                  Political Science
    ## 3042                       Horticulture
    ## 3043                                Art
    ## 3044      Planning &amp; Landscape Arch
    ## 3045                  Computer Sciences
    ## 3046                          Geography
    ## 3047          Animal And Dairy Sciences
    ## 3048                 Communication Arts
    ## 3049                         Geoscience
    ## 3050                         Pediatrics
    ## 3051  Biostatistics&amp;Med Informatics
    ## 3052         Department Of Neuroscience
    ## 3053             Biomedical Engineering
    ## 3054      Engr Professional Development
    ## 3055                              Dance
    ## 3056                           Genetics
    ## 3057                  Computer Sciences
    ## 3058                        Social Work
    ## 3059                  Surgical Sciences
    ## 3060  Pathology&amp;Laboratory Medicine
    ## 3061                            Finance
    ## 3062  Rehab Psychology &amp; Special Ed
    ## 3063     Lafollette Sch Of Publ Affairs
    ## 3064                                Art
    ## 3065      Industrial &amp; Systems Engr
    ## 3066                 Information School
    ## 3067                         Law School
    ## 3068                 Information School
    ## 3069                            Nursing
    ## 3070                    Plant Pathology
    ## 3071             Acad&amp;Prg-Noncredit
    ## 3072                        Social Work
    ## 3073      Engr Professional Development
    ## 3074                           Medicine
    ## 3075                 Communication Arts
    ## 3076                          Economics
    ## 3077                          Geography
    ## 3078                         Pediatrics
    ## 3079                  Surgical Sciences
    ## 3080                        Mathematics
    ## 3081                          Chemistry
    ## 3082                          Economics
    ## 3083                 Information School
    ## 3084           Disease Prevention Admin
    ## 3085                       Food Science
    ## 3086                        Mathematics
    ## 3087                   Medical Sciences
    ## 3088                            Nursing
    ## 3089     Division Of Continuing Studies
    ## 3090                        Social Work
    ## 3091                  Surgical Sciences
    ## 3092                  Surgical Sciences
    ## 3093                                Art
    ## 3094                    Family Medicine
    ## 3095                         Philosophy
    ## 3096                        Mathematics
    ## 3097                          Economics
    ## 3098                  Computer Sciences
    ## 3099                       Soil Science
    ## 3100                            Nursing
    ## 3101                    Plant Pathology
    ## 3102        German, Nordic &amp; Slavic
    ## 3103                         Pediatrics
    ## 3104     Civil &amp; Environmental Engr
    ## 3105                  Ctr For Jewish St
    ## 3106                          Economics
    ## 3107                           Pharmacy
    ## 3108                        Mathematics
    ## 3109                  Surgical Sciences
    ## 3110                          Geography
    ## 3111                         Philosophy
    ## 3112                Engineering Physics
    ## 3113                        Mathematics
    ## 3114                             Botany
    ## 3115                        Art History
    ## 3116                   Academic Affairs
    ## 3117                    Medical Physics
    ## 3118                         Law School
    ## 3119                            Physics
    ## 3120                Theatre &amp; Drama
    ## 3121                Engineering Physics
    ## 3122  Ed Leadership&amp;Policy Analysis
    ## 3123                Engineering Physics
    ## 3124      Cell And Regenerative Biology
    ## 3125                  Surgical Sciences
    ## 3126             Spanish And Portuguese
    ## 3127                          Chemistry
    ## 3128   Management &amp; Human Resources
    ## 3129         Curriculum And Instruction
    ## 3130                       Anthropology
    ## 3131                        Kinesiology
    ## 3132        Obstetrics &amp; Gynecology
    ## 3133                          Astronomy
    ## 3134        Life Sciences Communication
    ## 3135                Integrative Biology
    ## 3136                            History
    ## 3137    Comp Lit &amp; Folklore Studies
    ## 3138                            History
    ## 3139                Theatre &amp; Drama
    ## 3140                        Mathematics
    ## 3141                            Nursing
    ## 3142                         Entomology
    ## 3143                         Philosophy
    ## 3144      Planning &amp; Landscape Arch
    ## 3145                    Family Medicine
    ## 3146                          Radiology
    ## 3147                   Medical Sciences
    ## 3148  Communication Sci &amp; Disorders
    ## 3149        German, Nordic &amp; Slavic
    ## 3150         Educational Policy Studies
    ## 3151      Engr Professional Development
    ## 3152 Agricultural&amp;Applied Economics
    ## 3153                         Law School
    ## 3154                              Dance
    ## 3155              Counseling Psychology
    ## 3156        Obstetrics &amp; Gynecology
    ## 3157 Agricultural&amp;Applied Economics
    ## 3158            Comparative Biosciences
    ## 3159        Life Sciences Communication
    ## 3160                         Law School
    ## 3161         Curriculum And Instruction
    ## 3162  Community &amp; Environ Sociology
    ## 3163              Counseling Psychology
    ## 3164                           Agronomy
    ## 3165                            History
    ## 3166  Materials Science&amp;Engineering
    ## 3167                                Art
    ## 3168                                Art
    ## 3169                        Mathematics
    ## 3170        Mead Witter School Of Music
    ## 3171                          Chemistry
    ## 3172                         Psychiatry
    ## 3173     Biological Systems Engineering
    ## 3174        German, Nordic &amp; Slavic
    ## 3175     Electrical &amp; Computer Engr
    ## 3176                        Kinesiology
    ## 3177                  Political Science
    ## 3178                        Mathematics
    ## 3179  Dept Of Med History&amp;Bioethics
    ## 3180                       Anthropology
    ## 3181                           Medicine
    ## 3182         Educational Policy Studies
    ## 3183                            Nursing
    ## 3184     Ms In Biotechnology Degree Prg
    ## 3185      Engr Professional Development
    ## 3186                        Social Work
    ## 3187                            Urology
    ## 3188                            History
    ## 3189             Biomedical Engineering
    ## 3190                       Bacteriology
    ## 3191                           Oncology
    ## 3192                        Mathematics
    ## 3193                          Economics
    ## 3194             Biomedical Engineering
    ## 3195               Nutritional Sciences
    ## 3196           Disease Prevention Admin
    ## 3197     Asian Languages &amp; Cultures
    ## 3198     Init For Studies In Trnfm Entr
    ## 3199             Mechanical Engineering
    ## 3200               Nutritional Sciences
    ## 3201             Acad&amp;Prg-Noncredit
    ## 3202                          Sociology
    ## 3203                       Biochemistry
    ## 3204                          Neurology
    ## 3205                           Oncology
    ## 3206            Comparative Biosciences
    ## 3207            Comparative Biosciences
    ## 3208                 Emergency Medicine
    ## 3209        Mead Witter School Of Music
    ## 3210                            English
    ## 3211     Chemical &amp; Biological Engr
    ## 3212               Risk &amp; Insurance
    ## 3213                   Medical Sciences
    ## 3214                       Religious St
    ## 3215     Ms In Biotechnology Degree Prg
    ## 3216                            History
    ## 3217                  Computer Sciences
    ## 3218                  Computer Sciences
    ## 3219               Risk &amp; Insurance
    ## 3220  Classic &amp; Ancient Near E Stds
    ## 3221                             Botany
    ## 3222  Materials Science&amp;Engineering
    ## 3223                          Economics
    ## 3224                  Political Science
    ## 3225                         Law School
    ## 3226                         Law School
    ## 3227                  Surgical Sciences
    ## 3228                        Social Work
    ## 3229           Pathobiological Sciences
    ## 3230             Accting &amp; Info Sys
    ## 3231      Cell And Regenerative Biology
    ## 3232                           Pharmacy
    ## 3233  Biostatistics&amp;Med Informatics
    ## 3234                     Design Studies
    ## 3235                          Marketing
    ## 3236                  Computer Sciences
    ## 3237  Rehab Psychology &amp; Special Ed
    ## 3238               Nutritional Sciences
    ## 3239                            English
    ## 3240      Industrial &amp; Systems Engr
    ## 3241  Communication Sci &amp; Disorders
    ## 3242        Mead Witter School Of Music
    ## 3243                         Law School
    ## 3244        German, Nordic &amp; Slavic
    ## 3245  Classic &amp; Ancient Near E Stds
    ## 3246                           Pharmacy
    ## 3247         Curriculum And Instruction
    ## 3248                            Nursing
    ## 3249        Mead Witter School Of Music
    ## 3250           Pathobiological Sciences
    ## 3251             Spanish And Portuguese
    ## 3252                           Pharmacy
    ## 3253                    Family Medicine
    ## 3254                           Medicine
    ## 3255                         Pediatrics
    ## 3256   Management &amp; Human Resources
    ## 3257                            Physics
    ## 3258                        Mathematics
    ## 3259                          Wiscience
    ## 3260                            History
    ## 3261                  Surgical Sciences
    ## 3262                 Information School
    ## 3263                    Family Medicine
    ## 3264                       Food Science
    ## 3265                          Wiscience
    ## 3266             Mechanical Engineering
    ## 3267                 French And Italian
    ## 3268                         Psychiatry
    ## 3269                Engineering Physics
    ## 3270                            Surgery
    ## 3271                       Food Science
    ## 3272                        Mathematics
    ## 3273        Mead Witter School Of Music
    ## 3274  Materials Science&amp;Engineering
    ## 3275                Integrative Biology
    ## 3276            School Of Human Ecology
    ## 3277                       Bacteriology
    ## 3278             Accting &amp; Info Sys
    ## 3279                          Geography
    ## 3280     Biological Systems Engineering
    ## 3281                          Marketing
    ## 3282             Mechanical Engineering
    ## 3283                        Kinesiology
    ## 3284           African Cultural Studies
    ## 3285              Counseling Psychology
    ## 3286                 Emergency Medicine
    ## 3287      Cell And Regenerative Biology
    ## 3288      Planning &amp; Landscape Arch
    ## 3289                         Geoscience
    ## 3290                  Surgical Sciences
    ## 3291               Nutritional Sciences
    ## 3292                            Physics
    ## 3293                     Human Oncology
    ## 3294                  Academic Programs
    ## 3295     Asian Languages &amp; Cultures
    ## 3296                         Geoscience
    ## 3297  Rehab Psychology &amp; Special Ed
    ## 3298                           Genetics
    ## 3299                            Physics
    ## 3300              Counseling Psychology
    ## 3301                        Kinesiology
    ## 3302                            English
    ## 3303                         Law School
    ## 3304     Civil &amp; Environmental Engr
    ## 3305       Wisconsin School Of Business
    ## 3306     Ctr For Rus East Eur Cent Asia
    ## 3307                         Philosophy
    ## 3308                   Medical Sciences
    ## 3309                         Law School
    ## 3310         Curriculum And Instruction
    ## 3311                 French And Italian
    ## 3312                  Surgical Sciences
    ## 3313                   Academic Affairs
    ## 3314                 Communication Arts
    ## 3315                   Academic Affairs
    ## 3316             Biomedical Engineering
    ## 3317  Operations &amp; Information Mgmt
    ## 3318              Counseling Psychology
    ## 3319                         Psychiatry
    ## 3320                 Information School
    ## 3321      Forest &amp; Wildlife Ecology
    ## 3322                          Astronomy
    ## 3323                           Agronomy
    ## 3324                        Mathematics
    ## 3325                        Kinesiology
    ## 3326                   Academic Affairs
    ## 3327     Lafollette Sch Of Publ Affairs
    ## 3328                          Astronomy
    ## 3329                   Medical Sciences
    ## 3330                             Botany
    ## 3331                  Academic Programs
    ## 3332                        Social Work
    ## 3333   Management &amp; Human Resources
    ## 3334  Rehab Psychology &amp; Special Ed
    ## 3335   Management &amp; Human Resources
    ## 3336                        Kinesiology
    ## 3337              Counseling Psychology
    ## 3338 Atmospheric &amp; Oceanic Sciences
    ## 3339                  Political Science
    ## 3340                            English
    ## 3341                         Entomology
    ## 3342                         Law School
    ## 3343             Mechanical Engineering
    ## 3344             General Administration
    ## 3345                                Art
    ## 3346                  Ctr For Jewish St
    ## 3347                          Marketing
    ## 3348        German, Nordic &amp; Slavic
    ## 3349       Se Asian Summer Studies Inst
    ## 3350                  Surgical Sciences
    ## 3351                         Law School
    ## 3352              Counseling Psychology
    ## 3353         Educational Policy Studies
    ## 3354                         Law School
    ## 3355                          Geography
    ## 3356                Integrative Biology
    ## 3357             Mechanical Engineering
    ## 3358             Biomedical Engineering
    ## 3359                  Computer Sciences
    ## 3360         Curriculum And Instruction
    ## 3361         Department Of Neuroscience
    ## 3362  Pathology&amp;Laboratory Medicine
    ## 3363  Ed Leadership&amp;Policy Analysis
    ## 3364              Counseling Psychology
    ## 3365  Ed Leadership&amp;Policy Analysis
    ## 3366                       Soil Science
    ## 3367                            History
    ## 3368                            History
    ## 3369            School Of Human Ecology
    ## 3370                   Medical Sciences
    ## 3371                        Social Work
    ## 3372           Gender And Women Studies
    ## 3373                        Mathematics
    ## 3374                         Geoscience
    ## 3375        Mead Witter School Of Music
    ## 3376                Theatre &amp; Drama
    ## 3377                  Surgical Sciences
    ## 3378                 Information School
    ## 3379        German, Nordic &amp; Slavic
    ## 3380      Forest &amp; Wildlife Ecology
    ## 3381     Electrical &amp; Computer Engr
    ## 3382                     Anesthesiology
    ## 3383                        Kinesiology
    ## 3384     Chemical &amp; Biological Engr
    ## 3385                            Nursing
    ## 3386                  Computer Sciences
    ## 3387          Animal And Dairy Sciences
    ## 3388                       Food Science
    ## 3389 Agricultural&amp;Applied Economics
    ## 3390                         Psychology
    ## 3391                         Law School
    ## 3392                 Communication Arts
    ## 3393                         Law School
    ## 3394  Classic &amp; Ancient Near E Stds
    ## 3395                            Physics
    ## 3396                Integrative Biology
    ## 3397                          Astronomy
    ## 3398                   Academic Affairs
    ## 3399     Electrical &amp; Computer Engr
    ## 3400        Mead Witter School Of Music
    ## 3401                            English
    ## 3402                          Neurology
    ## 3403             Lat Amer Carib Iber St
    ## 3404                    Medical Physics
    ## 3405                         Law School
    ## 3406                 French And Italian
    ## 3407  Ed Leadership&amp;Policy Analysis
    ## 3408                            Physics
    ## 3409      Industrial &amp; Systems Engr
    ## 3410  Communication Sci &amp; Disorders
    ## 3411                                Art
    ## 3412  Biostatistics&amp;Med Informatics
    ## 3413               Neurological Surgery
    ## 3414                  Computer Sciences
    ## 3415     Electrical &amp; Computer Engr
    ## 3416                       Soil Science
    ## 3417                       Biochemistry
    ## 3418     Ms In Biotechnology Degree Prg
    ## 3419                   Medical Sciences
    ## 3420                           Genetics
    ## 3421                          Chemistry
    ## 3422            Comparative Biosciences
    ## 3423     Ms In Biotechnology Degree Prg
    ## 3424         Curriculum And Instruction
    ## 3425                 French And Italian
    ## 3426     Chicana/O And Latina/O Studies
    ## 3427 Atmospheric &amp; Oceanic Sciences
    ## 3428                         Law School
    ## 3429                    Family Medicine
    ## 3430                           Pharmacy
    ## 3431                   Medical Sciences
    ## 3432             Educational Psychology
    ## 3433                            Nursing
    ## 3434                            Surgery
    ## 3435                         Law School
    ## 3436                         Law School
    ## 3437  Materials Science&amp;Engineering
    ## 3438                         Philosophy
    ## 3439      Vp Diversity And Climate Prog
    ## 3440     Civil &amp; Environmental Engr
    ## 3441           Gender And Women Studies
    ## 3442                        Mathematics
    ## 3443 Human Development&amp;Family Study
    ## 3444  Ed Leadership&amp;Policy Analysis
    ## 3445  Journalism&amp;Mass Communication
    ## 3446             Mechanical Engineering
    ## 3447                Theatre &amp; Drama
    ## 3448        Life Sciences Communication
    ## 3449                   Academic Affairs
    ## 3450 Atmospheric &amp; Oceanic Sciences
    ## 3451                           Medicine
    ## 3452                    Medical Physics
    ## 3453                          Astronomy
    ## 3454                         Psychiatry
    ## 3455                           Pharmacy
    ## 3456                            History
    ## 3457                        Mathematics
    ## 3458                        Mathematics
    ## 3459                              Dance
    ## 3460                          Economics
    ## 3461                   Medical Sciences
    ## 3462                            Physics
    ## 3463     Lafollette Sch Of Publ Affairs
    ## 3464                            Nursing
    ## 3465                  Surgical Sciences
    ## 3466                Administration-Vmth
    ## 3467        Mead Witter School Of Music
    ## 3468              Counseling Psychology
    ## 3469       Wisconsin School Of Business
    ## 3470  Real Estate &amp; Urgan Land Econ
    ## 3471                         Psychology
    ## 3472                   Academic Affairs
    ## 3473                        Social Work
    ## 3474        German, Nordic &amp; Slavic
    ## 3475                            History
    ## 3476                        Mathematics
    ## 3477     Civil &amp; Environmental Engr
    ## 3478  Biostatistics&amp;Med Informatics
    ## 3479                Integrative Biology
    ## 3480                 Communication Arts
    ## 3481                       Bacteriology
    ## 3482                            English
    ## 3483                         Statistics
    ## 3484                          Chemistry
    ## 3485      Industrial &amp; Systems Engr
    ## 3486  Materials Science&amp;Engineering
    ## 3487  Ed Leadership&amp;Policy Analysis
    ## 3488     Lafollette Sch Of Publ Affairs
    ## 3489                         Statistics
    ## 3490                       Horticulture
    ## 3491     Electrical &amp; Computer Engr
    ## 3492             Accting &amp; Info Sys
    ## 3493             Accting &amp; Info Sys
    ## 3494                            English
    ## 3495       Wisconsin School Of Business
    ## 3496                            Nursing
    ## 3497                         Psychology
    ## 3498         Curriculum And Instruction
    ## 3499             Accting &amp; Info Sys
    ## 3500                         Pediatrics
    ## 3501                            History
    ## 3502         Population Health Sciences
    ## 3503                           Genetics
    ## 3504                       Bacteriology
    ## 3505     Orthopedics And Rehabilitation
    ## 3506            Comparative Biosciences
    ## 3507          Animal And Dairy Sciences
    ## 3508       Wisconsin School Of Business
    ## 3509                Theatre &amp; Drama
    ## 3510      Cell And Regenerative Biology
    ## 3511                          Chemistry
    ## 3512                Integrative Biology
    ## 3513                             Botany
    ## 3514                       Biochemistry
    ## 3515                  Political Science
    ## 3516     Civil &amp; Environmental Engr
    ## 3517                          Radiology
    ## 3518          Animal And Dairy Sciences
    ## 3519                         Law School
    ## 3520     Lafollette Sch Of Publ Affairs
    ## 3521                          Marketing
    ## 3522                          Chemistry
    ## 3523                          Chemistry
    ## 3524               Medical Microbiology
    ## 3525                            Surgery
    ## 3526      Cell And Regenerative Biology
    ## 3527                            English
    ## 3528  Ed Leadership&amp;Policy Analysis
    ## 3529  Operations &amp; Information Mgmt
    ## 3530                       Anthropology
    ## 3531     Electrical &amp; Computer Engr
    ## 3532                          Chemistry
    ## 3533                       Horticulture
    ## 3534                    Family Medicine
    ## 3535                           Pharmacy
    ## 3536                          Economics
    ## 3537                           Agronomy
    ## 3538                           Genetics
    ## 3539              Afro-American Studies
    ## 3540      Industrial &amp; Systems Engr
    ## 3541      Engr Professional Development
    ## 3542      Engr Professional Development
    ## 3543                          Economics
    ## 3544                           Medicine
    ## 3545                       Biochemistry
    ## 3546                          Neurology
    ## 3547                     Human Oncology
    ## 3548                   Consumer Science
    ## 3549          Animal And Dairy Sciences
    ## 3550                  Academic Programs
    ## 3551                  Surgical Sciences
    ## 3552                            History
    ## 3553                       Soil Science
    ## 3554              Afro-American Studies
    ## 3555                            Nursing
    ## 3556                         Philosophy
    ## 3557                          Chemistry
    ## 3558                          Chemistry
    ## 3559             Acad&amp;Prg-Noncredit
    ## 3560                    Medical Physics
    ## 3561              Counseling Psychology
    ## 3562      Industrial &amp; Systems Engr
    ## 3563  Rehab Psychology &amp; Special Ed
    ## 3564        Mead Witter School Of Music
    ## 3565                         Law School
    ## 3566                 Information School
    ## 3567                          Astronomy
    ## 3568             Accting &amp; Info Sys
    ## 3569                       Biochemistry
    ## 3570                 Information School
    ## 3571  Rehab Psychology &amp; Special Ed
    ## 3572                Integrative Biology
    ## 3573         Curriculum And Instruction
    ## 3574             Biomedical Engineering
    ## 3575             Educational Psychology
    ## 3576                 Information School
    ## 3577                          Geography
    ## 3578                          Wiscience
    ## 3579                  Computer Sciences
    ## 3580             Biomedical Engineering
    ## 3581        Obstetrics &amp; Gynecology
    ## 3582   Management &amp; Human Resources
    ## 3583                          Economics
    ## 3584                Engineering Physics
    ## 3585                         Law School
    ## 3586                 Communication Arts
    ## 3587                   Academic Affairs
    ## 3588                            History
    ## 3589                        Social Work
    ## 3590                     Anesthesiology
    ## 3591                         Law School
    ## 3592                Engineering Physics
    ## 3593          Animal And Dairy Sciences
    ## 3594                            Nursing
    ## 3595                          Marketing
    ## 3596  Ed Leadership&amp;Policy Analysis
    ## 3597                         Psychology
    ## 3598                        Kinesiology
    ## 3599                          Economics
    ## 3600             Biomedical Engineering
    ## 3601  Ed Leadership&amp;Policy Analysis
    ## 3602                        Amer Ind St
    ## 3603        German, Nordic &amp; Slavic
    ## 3604        German, Nordic &amp; Slavic
    ## 3605                          Astronomy
    ## 3606             Accting &amp; Info Sys
    ## 3607             Educational Psychology
    ## 3608             Educational Psychology
    ## 3609            School Of Human Ecology
    ## 3610                            English
    ## 3611                   Medical Sciences
    ## 3612               Medical Microbiology
    ## 3613                          Chemistry
    ## 3614                             Botany
    ## 3615                          Geography
    ## 3616     Ms In Biotechnology Degree Prg
    ## 3617     Civil &amp; Environmental Engr
    ## 3618                       Biochemistry
    ## 3619                          Chemistry
    ## 3620                            Finance
    ## 3621                  Computer Sciences
    ## 3622                         Law School
    ## 3623              Counseling Psychology
    ## 3624                         Statistics
    ## 3625                        Mathematics
    ## 3626     Civil &amp; Environmental Engr
    ## 3627                         Law School
    ## 3628                            Physics
    ## 3629                   Academic Affairs
    ## 3630        Life Sciences Communication
    ## 3631                           Oncology
    ## 3632                        Social Work
    ## 3633                         Geoscience
    ## 3634      Industrial &amp; Systems Engr
    ## 3635                           Oncology
    ## 3636             Mechanical Engineering
    ## 3637                         Law School
    ## 3638                         Law School
    ## 3639     Lafollette Sch Of Publ Affairs
    ## 3640                Integrative Biology
    ## 3641                         Statistics
    ## 3642                         Statistics
    ## 3643  Journalism&amp;Mass Communication
    ## 3644                        Mathematics
    ## 3645                          Chemistry
    ## 3646        Engineering Research Center
    ## 3647  Real Estate &amp; Urgan Land Econ
    ## 3648                            Physics
    ## 3649               Nutritional Sciences
    ## 3650             Biomedical Engineering
    ## 3651                          Chemistry
    ## 3652                           Genetics
    ## 3653     Chemical &amp; Biological Engr
    ## 3654         Department Of Neuroscience
    ## 3655                          Chemistry
    ## 3656                 Information School
    ## 3657                         Entomology
    ## 3658                            History
    ## 3659                         Law School
    ## 3660                            English
    ## 3661                            English
    ## 3662                          Geography
    ## 3663                       Bacteriology
    ## 3664                              Dance
    ## 3665                          Radiology
    ## 3666                           Pharmacy
    ## 3667  Biostatistics&amp;Med Informatics
    ## 3668                            English
    ## 3669                  Computer Sciences
    ## 3670     Electrical &amp; Computer Engr
    ## 3671        German, Nordic &amp; Slavic
    ## 3672      Engr Professional Development
    ## 3673                      Naval Science
    ## 3674                         Geoscience
    ## 3675                           Medicine
    ## 3676                       Horticulture
    ## 3677           Pathobiological Sciences
    ## 3678                      Asian Studies
    ## 3679                          Chemistry
    ## 3680                         Pediatrics
    ## 3681                            Surgery
    ## 3682     Chemical &amp; Biological Engr
    ## 3683      Industrial &amp; Systems Engr
    ## 3684     Orthopedics And Rehabilitation
    ## 3685                  Academic Programs
    ## 3686             Accting &amp; Info Sys
    ## 3687                           Medicine
    ## 3688                          Chemistry
    ## 3689                        Mathematics
    ## 3690                              Dance
    ## 3691                         Statistics
    ## 3692  Pathology&amp;Laboratory Medicine
    ## 3693                         Statistics
    ## 3694  Real Estate &amp; Urgan Land Econ
    ## 3695     Asian Languages &amp; Cultures
    ## 3696                         Law School
    ## 3697                           Oncology
    ## 3698                          Astronomy
    ## 3699     Asian Languages &amp; Cultures
    ## 3700              Counseling Psychology
    ## 3701            School Of Human Ecology
    ## 3702                Engineering Physics
    ## 3703                         Statistics
    ## 3704     Biological Systems Engineering
    ## 3705            Comparative Biosciences
    ## 3706  Biostatistics&amp;Med Informatics
    ## 3707         Department Of Neuroscience
    ## 3708                  Computer Sciences
    ## 3709        Obstetrics &amp; Gynecology
    ## 3710                           Genetics
    ## 3711                  Computer Sciences
    ## 3712      Industrial &amp; Systems Engr
    ## 3713                       Anthropology
    ## 3714                          Geography
    ## 3715                  Computer Sciences
    ## 3716                         Statistics
    ## 3717     Asian Languages &amp; Cultures
    ## 3718     Civil &amp; Environmental Engr
    ## 3719                                Art
    ## 3720        German, Nordic &amp; Slavic
    ## 3721                        Mathematics
    ## 3722                            English
    ## 3723              Counseling Psychology
    ## 3724             Mechanical Engineering
    ## 3725           Pathobiological Sciences
    ## 3726                         Geoscience
    ## 3727                            Nursing
    ## 3728      Forest &amp; Wildlife Ecology
    ## 3729                        Social Work
    ## 3730                            Nursing
    ## 3731                  Political Science
    ## 3732                           Genetics
    ## 3733                        Kinesiology
    ## 3734              Counseling Psychology
    ## 3735                            English
    ## 3736                          Astronomy
    ##                                                degree
    ## 1                    PHD 1979 University of Edinburgh
    ## 2                        MD 2000 University of Assiut
    ## 3                       PHD 2012 Royal College of Art
    ## 4                  PHD 2013 Univ of Wisconsin-Madison
    ## 5                   MA 2017 Univ of Wisconsin-Madison
    ## 6                 PHD 1978 University of Pennsylvania
    ## 7                 MACC 2005 Univ of Wisconsin-Madison
    ## 8                  PHD 1987 Colorado State University
    ## 9              PHD 2008 Univ of Michigan at Ann Arbor
    ## 10                  PHD 2018 University of Washington
    ## 11                 DNP 2017 Univ of Wisconsin-Madison
    ## 12                    MA  University of South Florida
    ## 13                  PHD 2020 Univ of California Davis
    ## 14                 PHD 1998 Univ of Wisconsin-Madison
    ## 15                            PHD 2012 Ithaca College
    ## 16                 PHD 1989 Univ of Wisconsin-Madison
    ## 17                       MD 1989 University Of Aleppo
    ## 18                 PHD 2019 Univ of California Irvine
    ## 19                  MS 1997 Univ of Wisconsin-Madison
    ## 20                 PHD 2019 Univ of Wisconsin-Madison
    ## 21                 PHD 1981 Univ of Wisconsin-Madison
    ## 22                     PHD 1989 University of Lucknow
    ## 23               MD 2003 Loyola University of Chicago
    ## 24                     MA 2013 Ewha Womans University
    ## 25                   PHD  Univ of California Berkeley
    ## 26            MFA 2007 Maryland Institute Colg Of Art
    ## 27              MD 2002 U of California San Francisco
    ## 28               PHD 2019 Univ of California Berkeley
    ## 29                       JD 1972 Marquette University
    ## 30                PHD 2014 University of Pennsylvania
    ## 31                                              PHD  
    ## 32                PHD 2005 Carnegie-Mellon University
    ## 33                     PHD 2012 University of Alberta
    ## 34                         MD 2005 Al-Quds University
    ## 35                  PHD 2004 University of Pittsburgh
    ## 36               PHD 1991 Univ of California Berkeley
    ## 37                        PHD 2002 Cornell University
    ## 38                     PHD 2014 University of Toronto
    ## 39                  PHD 2002 Arizona State University
    ## 40            PHD 2006 Univ of IL at Urbana-Champaign
    ## 41                      MD 1984 University of Vermont
    ## 42                PHD 1994 Univ Complutense de Madrid
    ## 43                 PHD 1974 Michigan State University
    ## 44            PHD 2009 Univ of California Los Angeles
    ## 45                     PHD 1994 University of Arizona
    ## 46              MA 2007 University Of Central Florida
    ## 47                 PHD 2018 Univ of Wisconsin-Madison
    ## 48                                           BA 2002 
    ## 49                                              PHD  
    ## 50                     PHD 1994 University of Chicago
    ## 51             PHD 2003 Univ of Michigan at Ann Arbor
    ## 52         PHD 1987 VA Polytechnic Inst &amp; State U
    ## 53                            MD 1980 Duke University
    ## 54                          PHD 2002 Emory University
    ## 55                PHD 2005 Georgia Inst of Technology
    ## 56                           PHD 2006 Duke University
    ## 57                  MS 1983 Univ of Wisconsin-Madison
    ## 58                 PHD 2002 Univ of Wisconsin-Madison
    ## 59              PHD 2002 Cleveland Institute Of Music
    ## 60                 PHD 2006 Univ of Wisconsin-Madison
    ## 61             PHD 1996 Pennsylvania State University
    ## 62                 PHD 2013 Univ of Wisconsin-Madison
    ## 63                 DVM 2003 Michigan State University
    ## 64                     PHD  Univ of Wisconsin-Madison
    ## 65                         PHD 2007 Baylor University
    ## 66                 PHD 1999 Univ of Wisconsin-Madison
    ## 67                        PHD 1982 Indiana University
    ## 68                 PHD 2018 Univ of Wisconsin-Madison
    ## 69                        PHD 2011 Indiana University
    ## 70                 MS 2007 Georgia Inst of Technology
    ## 71                           PHD 2019 Ohio University
    ## 72                      PHD 2018 University of Kansas
    ## 73             PHD 2014 Univ of Michigan at Ann Arbor
    ## 74                 PHD 2004 Univ of Wisconsin-Madison
    ## 75                    PHD 2015 University of Helsinki
    ## 76                 PHD 1984 Univ of Wisconsin-Madison
    ## 77                           PHD 2005 Duke University
    ## 78                 PHD 2019 Univ of Wisconsin-Madison
    ## 79                 PHD 2006 Univ of Wisconsin-Madison
    ## 80                 PHD 1998 Univ of Wisconsin-Madison
    ## 81                  MS 1995 Univ of Wisconsin-Madison
    ## 82             PHD 1982 Univ of Minnesota-Twin Cities
    ## 83            PHD 1999 Univ of Dublin-Trinity College
    ## 84                  MD 1992 Univ of Missouri-Columbia
    ## 85             PHD 2015 Univ of Alabama at Birmingham
    ## 86            PHD 2014 University Of Texas At El Paso
    ## 87                           PHD 2019 Duke University
    ## 88                 MBA 2004 Univ of Wisconsin-Madison
    ## 89               PHD 2010 Univ of California Berkeley
    ## 90                    PHD 2001 University of Delaware
    ## 91              PHD 2000 U de Toulouse II (Le Mirail)
    ## 92              PHD 2002 U de Toulouse II (Le Mirail)
    ## 93                  PHD 1995 Univ of California Davis
    ## 94                      PHD 1986 State Univ Of Leiden
    ## 95              DVM 1999 Univ Ncnl Autonoma de Mexico
    ## 96            MFA 1991 Sch Of The Art Inst Of Chicago
    ## 97                  MS 2020 Univ of Wisconsin-Madison
    ## 98              MSN 2007 Univ of Wisconsin-Eau Claire
    ## 99                                           M.PHIL  
    ## 100                 BS 2013 Univ of Wisconsin-Madison
    ## 101                  PHD 1995 Northwestern University
    ## 102                   MD 2008 University Of Rochester
    ## 103               MS 1996 Univ of Wisconsin-Green Bay
    ## 104                      PHD 1971 Columbia University
    ## 105                          PHD 2017 Yale University
    ## 106                          PHD  Stanford University
    ## 107                PHD 2002 Univ of Wisconsin-Madison
    ## 108                 MA 1972 Univ of Wisconsin-Madison
    ## 109                           PHD  Harvard University
    ## 110                    PHD 2011 Georgetown University
    ## 111                   PHD 2013 University of Virginia
    ## 112                 MD 2005 Univ of Wisconsin-Madison
    ## 113                  PHD 2006 Northwestern University
    ## 114                DPT 1994 Univ of Wisconsin-Madison
    ## 115                    PHD 1995 Ohio State University
    ## 116              PHD 1998 Univ of California Berkeley
    ## 117              PHD 1998 Univ of California Berkeley
    ## 118                PHD 2000 Univ of Wisconsin-Madison
    ## 119        PHD 2013 VA Polytechnic Inst &amp; State U
    ## 120           MFA 2000 Pennsylvania Acad Of Fine Arts
    ## 121                                         PHD 2014 
    ## 122                  PHD 1998 Northwestern University
    ## 123              PHD 2014 Univ of California Berkeley
    ## 124              PHD 2007 Rensselaer Polytechnic Inst
    ## 125                      EDD 2015 University of Leeds
    ## 126                       PHD 1995 University of Iowa
    ## 127                PHD 1994 Univ of Wisconsin-Madison
    ## 128                 PHD 2000 Johns Hopkins University
    ## 129                         MSN 2009 Edgewood College
    ## 130                  PHD 1995 University of Cambridge
    ## 131             PHD 1980 Univ of California San Diego
    ## 132                       PHD 2012 Cornell University
    ## 133             PHD 2002 Univ of California San Diego
    ## 134                 PHD 1981 University of Washington
    ## 135            PHD 1998 Univ of Massachusetts Amherst
    ## 136              MD 1997 Medical College Of Wisconsin
    ## 137                PHD 2010 Univ of Wisconsin-Madison
    ## 138                MS 2003 Carnegie-Mellon University
    ## 139              PHD 2009 Univ of Southern California
    ## 140              PHD 2012 Univ of California Berkeley
    ## 141                  MD 2005 University of Washington
    ## 142                    PHD 2004 Georgetown University
    ## 143         PHD 2009 Uni Pierre&amp;Marie Curie Paris
    ## 144                  PHD  Univ of Illinois at Chicago
    ## 145                PHD 2011 Univ of Wisconsin-Madison
    ## 146                 MFA 2014 University of Cincinnati
    ## 147                  MD 2012 University of Cincinnati
    ## 148            PHD 2020 Univ of Minnesota-Twin Cities
    ## 149               PHD 1987 Massachusetts Inst Of Tech
    ## 150              PHD 1984 Univ of California Berkeley
    ## 151                DVM 2000 Univ Of Minnesota-St Paul
    ## 152                        MPH 2008 Tulane University
    ## 153                 PHD 2007 University of Washington
    ## 154            PHD 1991 Pennsylvania State University
    ## 155                              PHD  Yale University
    ## 156        MA 2013 Clg of William &amp; Mary-Virginia
    ## 157                                          JD 2013 
    ## 158           PHD 2008 University of British Columbia
    ## 159                 MS 2009 Univ of Wisconsin-Madison
    ## 160                PHD 1997 Univ of Wisconsin-Madison
    ## 161                PHD 2001 Univ of Wisconsin-Madison
    ## 162                PHD 1998 Univ of Wisconsin-Madison
    ## 163             PHD 1998 Univ of California San Diego
    ## 164                 PHD 2009 Arizona State University
    ## 165                          PHD 1982 Yale University
    ## 166                    PHD 1994 University of Warwick
    ## 167             PHD 1998 Univ of California San Diego
    ## 168                      PHD 2012 Columbia University
    ## 169              EDM 2016 Univ of Wisconsin-La Crosse
    ## 170                                         MBA 2013 
    ## 171             PHD 2017 George Washington University
    ## 172                      PHD 1999 University of Idaho
    ## 173                       PHD 2018 Harvard University
    ## 174            PHD 2003 Univ of MD-University College
    ## 175                PHD 1992 Univ of Wisconsin-Madison
    ## 176           PHD 1987 Hebrew University of Jerusalem
    ## 177                 PHD 2000 Univ of California Davis
    ## 178                      JD 2006 Marquette University
    ## 179            PHD 2016 Univ of Massachusetts Amherst
    ## 180               MD 1989 Univ of Illinois at Chicago
    ## 181                       PHD 1997 Harvard University
    ## 182                        PHD 2000 Boston University
    ## 183                  PHD 1997 University of Cambridge
    ## 184             PHD 1963 Pennsylvania State U-Hershey
    ## 185                      PHD 1988 Stanford University
    ## 186                                JD  Boston College
    ## 187                 JD 2009 Univ of Wisconsin-Madison
    ## 188            PHD 2004 Leeds Metropolitan University
    ## 189                                         PHD 2002 
    ## 190            PHD 2009 University of Texas at Austin
    ## 191             PHARMD 2004 Univ of Wisconsin-Madison
    ## 192                PHD 1992 Univ of Wisconsin-Madison
    ## 193                PHD 2019 Univ of Wisconsin-Madison
    ## 194                PHD 1997 Univ of Wisconsin-Madison
    ## 195            MFA 1997 Univ of Michigan at Ann Arbor
    ## 196                   BA 1978 Evergreen State College
    ## 197                PHD 2003 Rutgers State Univ-Newark
    ## 198           PHD 2007 University of British Columbia
    ## 199                PHD 1997 Univ of Wisconsin-Madison
    ## 200               MACC 2020 Univ of Wisconsin-Madison
    ## 201                PHD 2004 Univ of Wisconsin-Madison
    ## 202                DVM 2017 Univ of Wisconsin-Madison
    ## 203                     MD 1995 University of Arizona
    ## 204                PHD 2001 Univ Of NC At Chapel Hill
    ## 205                 DS 2013 Univ of Wisconsin-Madison
    ## 206                MS 1989 University of North Dakota
    ## 207             PHD 1999 California Institute of Tech
    ## 208                         MD 1987 Ankara University
    ## 209                PHD 2010 University Of Mississippi
    ## 210                      PHD 2019 Stanford University
    ## 211               PHD 2013 University of Pennsylvania
    ## 212           PHD 1998 Univ of IL at Urbana-Champaign
    ## 213                        MD 2012 University of Iowa
    ## 214               PHD 2017 Massachusetts Inst Of Tech
    ## 215                           DS 2007 Universitat Ulm
    ## 216                        MA 2003 Harvard University
    ## 217                    PHD 1991 Washington University
    ## 218                                         MS2 2009 
    ## 219                 PHD 1993 Johns Hopkins University
    ## 220               PHD 2014 University of Pennsylvania
    ## 221             PHD 1993 Univ of TX Health Sci Center
    ## 222                    PHD 2008 Vanderbilt University
    ## 223                       PHD 2019 Cornell University
    ## 224                 MS 2011 Univ of Wisconsin-Madison
    ## 225              MD 1999 Loyola University of Chicago
    ## 226              PHD 2014 Univ of California Berkeley
    ## 227                      PHD 2006 New York University
    ## 228               PHD 1998 Massachusetts Inst Of Tech
    ## 229                      PHD 2012 Stanford University
    ## 230                     MA  Univ of Wisconsin-Madison
    ## 231                MA  Sch Of The Art Inst Of Chicago
    ## 232                PHD 2016 Univ of Wisconsin-Madison
    ## 233                PHD 1992 Michigan State University
    ## 234              PHD 2008 Rensselaer Polytechnic Inst
    ## 235                PHD 1994 Univ of Wisconsin-Madison
    ## 236              MS 2004 Univ of Wisconsin-Whitewater
    ## 237                   PHD 1989 University of Virginia
    ## 238            PHD 2006 Univ of Michigan at Ann Arbor
    ## 239                PSYD 2014 North Central University
    ## 240               MLIS 2016 Univ of Wisconsin-Madison
    ## 241                                           OQUAL  
    ## 242                    PHD 1998 University of Chicago
    ## 243                PHD 2010 Univ Of NC At Chapel Hill
    ## 244                          PHD 1992 Yale University
    ## 245                                              MS  
    ## 246                PHD 2001 University of Connecticut
    ## 247                PHD 2017 University of  Birmingham
    ## 248                 PHD 1991 Arizona State University
    ## 249             MD 2004 Univ of Minnesota-Twin Cities
    ## 250                    PHD 2006 University of Arizona
    ## 251                PHD 2002 Univ Of NC At Chapel Hill
    ## 252            PHD 2010 University of Texas at Austin
    ## 253                PHD 2014 Univ of Wisconsin-Madison
    ## 254                    PHD 1996 University Of Memphis
    ## 255                 JD 2008 Univ of Wisconsin-Madison
    ## 256                         MD 2002 Dartmouth College
    ## 257               PHD 1989 Massachusetts Inst Of Tech
    ## 258                    DVM 1993 University of Florida
    ## 259                         MD 1984 Temple University
    ## 260                      PHD 2002 Columbia University
    ## 261                      PHD 1994 SUNY At Stony Brook
    ## 262        PHD 1997 VA Polytechnic Inst &amp; State U
    ## 263                  PHD 2008 Northwestern University
    ## 264                  PHD 2008 Northwestern University
    ## 265                PHD 1995 Univ of Wisconsin-Madison
    ## 266                      PHD 1991 SUNY At Stony Brook
    ## 267                 MS 2011 Univ of Wisconsin-Madison
    ## 268                 MD 1989 Univ of Wisconsin-Madison
    ## 269                    PHD 1988 University of Florida
    ## 270               PHD 2004 Texas A &amp; M University
    ## 271                    PHD 1992 University of Chicago
    ## 272                   PHD 2007 Ecole Centrale de Lyon
    ## 273                PHD 1976 Univ of Wisconsin-Madison
    ## 274                 BFA  Univ of Wisconsin-Whitewater
    ## 275                          PHD 2007 Yale University
    ## 276              PHD 2006 Univ of California Berkeley
    ## 277                PHD 1973 Univ of Wisconsin-Madison
    ## 278                 BA 2019 Univ of Wisconsin-Madison
    ## 279                 MA 2009 Univ of Wisconsin-Madison
    ## 280              PHD 1995 Univ of California Berkeley
    ## 281             PHD 1992 Univ of Nebraska Medical Ctr
    ## 282                 PHD 1993 University of Cincinnati
    ## 283                      PHD 2010 Stanford University
    ## 284               PHD 1983 Massachusetts Inst Of Tech
    ## 285                       PHD 1990 University of Iowa
    ## 286                 JD 1993 Univ of Wisconsin-Madison
    ## 287             MD 1999 Johannes Gutenburg Univ Mainz
    ## 288                 JD 2001 Univ of Wisconsin-Madison
    ## 289                     PHD 1987 University of London
    ## 290                 MS 2007 Univ of Wisconsin-Madison
    ## 291             PHD 1999 Medical College Of Wisconsin
    ## 292                 PHD 2015 University of Pittsburgh
    ## 293                PHD 2000 Univ of Wisconsin-Madison
    ## 294                    MFA 2010 University Of Houston
    ## 295              PHD 2011 Univ of California Berkeley
    ## 296                PHD 2019 Univ of Wisconsin-Madison
    ## 297           DVM 1978 Univ of IL at Urbana-Champaign
    ## 298                        PHD 2005 Boston University
    ## 299             PHD 1999 California Institute of Tech
    ## 300              PHD 1982 Univ of California Berkeley
    ## 301                 MD 2006 Univ of Wisconsin-Madison
    ## 302                         MSN 2010 Edgewood College
    ## 303                     PHD 1994 Princeton University
    ## 304                 MS 2010 Univ of Wisconsin-Madison
    ## 305                       PHD 1984 Cornell University
    ## 306           DVM 2005 Univ of IL at Urbana-Champaign
    ## 307                       PHD 2018 Harvard University
    ## 308               PHD 2006 Univ of Colorado at Denver
    ## 309                PHD 2012 Univ of Wisconsin-Madison
    ## 310                      PHD 1998 Stanford University
    ## 311                           DPT  Arcadia University
    ## 312                    MS 1981 Wayne State University
    ## 313                 MS 2000 Univ of Wisconsin-Madison
    ## 314           PHD 2009 Hebrew University of Jerusalem
    ## 315                                             PHD  
    ## 316                 MS 2002 Univ of Wisconsin-Madison
    ## 317                 BS 2000 Univ of Wisconsin-Madison
    ## 318                       PHD 1989 Cornell University
    ## 319                         MBA 1991 Edgewood College
    ## 320                MSW 1988 Univ of Wisconsin-Madison
    ## 321                         MBA 1991 Edgewood College
    ## 322                PHD 1991 Univ of Wisconsin-Madison
    ## 323                PHD 2013 Univ of Wisconsin-Madison
    ## 324            PHD 2019 Louisiana State U-Baton Rouge
    ## 325                 JD 1982 Univ of Wisconsin-Madison
    ## 326                PHD 2013 Univ of Wisconsin-Madison
    ## 327                     PHD 1999 Princeton University
    ## 328                PHD 2007 Univ of Wisconsin-Madison
    ## 329           PHD 1999 Univ of IL at Urbana-Champaign
    ## 330                 PHD  Universite de l'Etat a Liege
    ## 331                    MSN 2005 University of Phoenix
    ## 332                PHD 2013 Univ of Wisconsin-Madison
    ## 333             PHD 1992 California Institute of Tech
    ## 334              MD 2009 Loyola University of Chicago
    ## 335                PHD 2014 North Carolina State Univ
    ## 336            PHD 1985 Univ of Michigan at Ann Arbor
    ## 337                PHD 2011 Univ of Wisconsin-Madison
    ## 338               PHD 2014 Trinity Western University
    ## 339                                              MA  
    ## 340                      PHD 2007 Columbia University
    ## 341                PHD 2018 Univ of Wisconsin-Madison
    ## 342              PHD 1988 Univ of California Berkeley
    ## 343                PHD 2012 Univ of Wisconsin-Madison
    ## 344              PHD 1976 Univ of California Berkeley
    ## 345              BS 1983 Univ of Wisconsin-Whitewater
    ## 346                 JD 1977 Univ of Wisconsin-Madison
    ## 347               MSSW 2005 Univ of Wisconsin-Madison
    ## 348            PHD 1995 Univ of Michigan at Ann Arbor
    ## 349                PHD 2018 Univ of Wisconsin-Madison
    ## 350            PHD 1983 U de Provence Aix-Marseille I
    ## 351                        PHD  University of Toronto
    ## 352            PHD 1993 Univ of California Santa Cruz
    ## 353                PHD 2000 Virginia State University
    ## 354                           JD 2002 Yale University
    ## 355                PHD 1992 Univ of Wisconsin-Madison
    ## 356            PHD 1984 U of California San Francisco
    ## 357                    PHD 1988 University of Chicago
    ## 358              PHD 2018 City University Of New York
    ## 359                PHD 2006 Univ of Wisconsin-Madison
    ## 360            PHD 2007 University of Texas at Austin
    ## 361                PHD 2005 Univ of Wisconsin-Madison
    ## 362                      MA 1990 Marquette University
    ## 363                PHD 2014 Univ of Wisconsin-Madison
    ## 364                 MS 2006 Univ of Wisconsin-Madison
    ## 365              PHD 1986 Univ of California Berkeley
    ## 366                 MD 1999 Univ of Wisconsin-Madison
    ## 367                MBA 2002 Univ of Wisconsin-Madison
    ## 368                PHD 1996 Univ of Wisconsin-Madison
    ## 369                      PHD 1984 Columbia University
    ## 370                          PHD 1987 Yale University
    ## 371              PHD 2010 Univ of California Berkeley
    ## 372             MD 1983 U of California San Francisco
    ## 373                PHD 2009 Univ of Wisconsin-Madison
    ## 374              PHD 1994 Univ of Colorado at Boulder
    ## 375               MSSW 1982 Univ of Wisconsin-Madison
    ## 376                PHD 2020 Univ of Wisconsin-Madison
    ## 377                          PHD 2017 Yale University
    ## 378            MLIS 1993 Northern Illinois University
    ## 379                                          JD 2010 
    ## 380                MSW 2012 Univ of Wisconsin-Madison
    ## 381                  BS 1979 University of Notre Dame
    ## 382                          PHD 1986 York University
    ## 383                PHD 2013 Univ of Wisconsin-Madison
    ## 384                 BS 1975 Univ of Wisconsin-Madison
    ## 385            PHD 1989 Univ of Michigan at Ann Arbor
    ## 386                DMV 2012 Univ of Wisconsin-Madison
    ## 387                 MS 2018 Univ of Wisconsin-Madison
    ## 388             MA 2012 University of Texas at Austin
    ## 389              PHD 1991 Univ of Southern California
    ## 390             MLIS 2014 Univ of Wisconsin-Milwaukee
    ## 391                      PHD 2000 University of Leeds
    ## 392                        JD 1989 Harvard University
    ## 393                          PHD 2012 Yale University
    ## 394              PHD 1997 Univ of California Berkeley
    ## 395               PHD 1991 Massachusetts Inst Of Tech
    ## 396            PHD 2015 University of Texas at Austin
    ## 397                 MD 2005 Univ of Wisconsin-Madison
    ## 398              MD 2002 Medical College Of Wisconsin
    ## 399                  DVM 2011 Kansas State University
    ## 400                       PHD 2002 Cornell University
    ## 401                       DVM 1999 Utrecht University
    ## 402             PHD 1986 Univ of California San Diego
    ## 403                    PHD 1979 University of Chicago
    ## 404                      PHD 1984 Stanford University
    ## 405                       JD 2007 New York University
    ## 406                          MD 2006 Brown University
    ## 407              PHD 2013 Univ of Southern California
    ## 408               PHD 2010 Univ of Tennessee, Memphis
    ## 409                    PHD  Univ of Wisconsin-Madison
    ## 410                PHD 2014 Univ of Wisconsin-Madison
    ## 411                  MD 1996 University of Washington
    ## 412               MSSW 1999 Univ of Wisconsin-Madison
    ## 413              PHD 2015 Univ of California Berkeley
    ## 414                        PHD 1997 Universitat Berne
    ## 415                DNP 2012 Univ of Wisconsin-Madison
    ## 416                 MS 2015 Univ of Wisconsin-Madison
    ## 417                         PHD 1988 Brown University
    ## 418                 DS 2018 Univ of Wisconsin-Madison
    ## 419                 JD 1993 Univ of Wisconsin-Madison
    ## 420                    MA 2016 Alfred Adler Institute
    ## 421                PHD 2011 Univ of Wisconsin-Madison
    ## 422                       PHD 2003 University of Utah
    ## 423                MBA 2003 Univ of Wisconsin-Madison
    ## 424                         PHD 1980 Universitat Wien
    ## 425                    AUD 2006 University of Florida
    ## 426            MFA 1996 Univ of Minnesota-Twin Cities
    ## 427                 PHD 2013 Johns Hopkins University
    ## 428                 PHD 2013 Georgia State University
    ## 429                       PHD 2017 Cornell University
    ## 430              PHD 1982 Univ of California Berkeley
    ## 431                    PHD 1998 Ohio State University
    ## 432               PHD 1994 Univ of Colorado at Denver
    ## 433                       PHD 1969 Harvard University
    ## 434               MACC 2020 Univ of Wisconsin-Madison
    ## 435           PHD 2015 Eidgenossische Tec Hoch Zurich
    ## 436                        PHD 1998 Auburn University
    ## 437                  PHD 2001 University Of Rochester
    ## 438                PHD 2003 Univ of Wisconsin-Madison
    ## 439                MSW 2004 Univ of Wisconsin-Madison
    ## 440                      PHD 1979 Syracuse University
    ## 441               EDD 2014 St Marys Univ of Minnesota
    ## 442                PHD 2008 Univ of Wisconsin-Madison
    ## 443           PHD 1986 Univ of California Los Angeles
    ## 444                         PHD 2014 University of MI
    ## 445                    PHD 2014 University of Georgia
    ## 446               PHD 2003 Massachusetts Inst Of Tech
    ## 447                 PHD 2020 University of Notre Dame
    ## 448             PHD 2020 Univ of Tennessee, Knoxville
    ## 449                                              MS  
    ## 450                 MD 1966 Univ of Wisconsin-Madison
    ## 451             MA 2019 Univ of Minnesota-Twin Cities
    ## 452                    PHD 1995 University of Vermont
    ## 453                 BS 2018 Univ of Wisconsin-Madison
    ## 454                    PHD 2000 Ohio State University
    ## 455                          PHD 2019 Yale University
    ## 456                PHD 2014 Univ of Wisconsin-Madison
    ## 457                                              MA  
    ## 458                         MS 2009 Drexel University
    ## 459                    PHD 2004 University of Florida
    ## 460                  PHD 2011 Northwestern University
    ## 461              PHD 1991 Univ of California Berkeley
    ## 462                       PHD 1986 Cornell University
    ## 463             PHD 2004 Univ of California San Diego
    ## 464                       PHD 2000 Cornell University
    ## 465                PHD 2010 Univ of Wisconsin-Madison
    ## 466                  MM 1975 Univ Of NC At Greensboro
    ## 467                     PHD 1988 University of Denver
    ## 468                   PHD 2012 University of Delaware
    ## 469                  PHD 2012 Northwestern University
    ## 470                       PHD 1982 Harvard University
    ## 471                    PHD 2011 Washington University
    ## 472                 MFA  Univ of California San Diego
    ## 473                PHD 1996 Univ Of NC At Chapel Hill
    ## 474                     BVM 2009 University of London
    ## 475                    MBA 1992 Washington University
    ## 476                          PHD 1992 Yale University
    ## 477                MFA 2006 Univ of Wisconsin-Madison
    ## 478                         BS 2021 Excelsior College
    ## 479            PHD 1987 Univ of Minnesota-Twin Cities
    ## 480            PHD 2010 University of Texas at Austin
    ## 481               MACC 2020 Univ of Wisconsin-Madison
    ## 482                   MD 2002 University Of Rochester
    ## 483                          MS 2015 Edgewood College
    ## 484                PHD 1988 Univ of Wisconsin-Madison
    ## 485                PHD 2016 Univ of Wisconsin-Madison
    ## 486                MD 2006 Virginia Commonwealth Univ
    ## 487                PHD 1990 Univ of Wisconsin-Madison
    ## 488                      PHD 2010 Stanford University
    ## 489                 PHD 1983 Univ of California Davis
    ## 490                PHD 2004 Michigan State University
    ## 491                    PHD 1984 University of Chicago
    ## 492                                          MS 1988 
    ## 493            PHD 1999 Univ of Michigan at Ann Arbor
    ## 494             MD 1995 Univ of Michigan at Ann Arbor
    ## 495                PHD 2006 Univ of Wisconsin-Madison
    ## 496                        JD 2002 University of Iowa
    ## 497                                          MS 2018 
    ## 498                      PHD 1991 Stanford University
    ## 499                PHD 2018 Univ of Wisconsin-Madison
    ## 500                           MA 1968 Yale University
    ## 501                       PHD 2010 Harvard University
    ## 502               PHD 2017 University of Pennsylvania
    ## 503                       PHD 1999 Harvard University
    ## 504                       JD 1999 Stanford University
    ## 505            PHD 1992 Univ of California Santa Cruz
    ## 506             MSN 2000 Loyola University of Chicago
    ## 507              MD 1996 Loyola University of Chicago
    ## 508              MS 2005 Univ of Wisconsin-Eau Claire
    ## 509             PHD 1996 California Institute of Tech
    ## 510                DVM 2017 Univ of Wisconsin-Madison
    ## 511                PHD 2016 Univ of Wisconsin-Madison
    ## 512                        MD 1996 Marmara University
    ## 513                        MS 2011 Capella University
    ## 514           PHD 2008 Univ of IL at Urbana-Champaign
    ## 515                      BA 2013 Marquette University
    ## 516                    PHD 2007 University of Chicago
    ## 517              MD 2000 Medical College Of Wisconsin
    ## 518                MD 2007 Baylor College Of Medicine
    ## 519                PHD 2010 Univ of Wisconsin-Madison
    ## 520                    EDD 1990 University of Florida
    ## 521                      PHD 2013 Columbia University
    ## 522           PHD 2008 Univ of California Los Angeles
    ## 523                    PHD 2018 University of Chicago
    ## 524                     MA 1990 University of Chicago
    ## 525                                    PHD 1998 India
    ## 526                PHD 1993 Univ of Wisconsin-Madison
    ## 527                     JD 2007 University of Chicago
    ## 528                  PHD 2012 Northwestern University
    ## 529             PHD 2008 Univ of TX Health Sci Center
    ## 530                 MS 2018 Univ of Wisconsin-Madison
    ## 531               PHD 2000 University of Pennsylvania
    ## 532            PHD 2019 Louisiana State U-Baton Rouge
    ## 533                 PHD 1992 University of Washington
    ## 534                 MD 2008 Univ of Wisconsin-Madison
    ## 535                    PHD 1990 University of Chicago
    ## 536                PHD 2009 Univ Of NC At Chapel Hill
    ## 537                       JD 1982 Columbia University
    ## 538                       PHD 2019 Cornell University
    ## 539                MFA 2015 North Carolina State Univ
    ## 540                PHD 1978 Univ of Missouri-Columbia
    ## 541            PHD 1992 University of Texas at Austin
    ## 542                       PHD 1985 University of Utah
    ## 543               PHD 2005 Carnegie-Mellon University
    ## 544                PHD 2012 Univ of Wisconsin-Madison
    ## 545                          PHD  SUNY At Stony Brook
    ## 546                       PHD 2000 University of Utah
    ## 547                PHD 2014 Univ Of NC At Chapel Hill
    ## 548                PHD 2016 Univ of Wisconsin-Madison
    ## 549                      PHD 2019 Stanford University
    ## 550                PHD 2009 Zhejiang Univ of Sciences
    ## 551                      PHD 2016 New York University
    ## 552                                          MS 2010 
    ## 553                PHD 2004 Univ of California Irvine
    ## 554                MFA 2017 Univ of Wisconsin-Madison
    ## 555                PHD 2016 Colorado State University
    ## 556                       PHD 1996 Harvard University
    ## 557                PHD 1973 Univ of Wisconsin-Madison
    ## 558                    PHD 2020 Vanderbilt University
    ## 559               PHD 2006 Georgia Inst of Technology
    ## 560             PHD 2004 Southern IL Univ.-Carbondale
    ## 561              PHD 1991 Univ of California Berkeley
    ## 562            PHD 2015 Univ of Michigan at Ann Arbor
    ## 563                        MM 1973 Indiana University
    ## 564                 PHD 1977 University of Washington
    ## 565                       PHD 2012 University of Iowa
    ## 566                PHD 1990 Colorado State University
    ## 567                PHD 2000 Michigan State University
    ## 568                         PHD 2011 Emory University
    ## 569              PHD 2003 Univ of California Berkeley
    ## 570                                          MA 2013 
    ## 571                       MA 2009 University of Leeds
    ## 572                       PHD 2013 Harvard University
    ## 573              MFA 2006 Univ of Wisconsin-Milwaukee
    ## 574                      JD 1985 Marquette University
    ## 575                EDM 2012 Univ of Wisconsin-Madison
    ## 576                PHD 1994 Univ of Wisconsin-Madison
    ## 577                PHD 2011 Univ of Wisconsin-Madison
    ## 578                    PHD 2016 Ohio State University
    ## 579                        PHD 2001 Purdue University
    ## 580                PHD 2017 Michigan State University
    ## 581                DVM 1991 Univ of Wisconsin-Madison
    ## 582                    PHD 1998 University of Chicago
    ## 583               PHD 2013 Carnegie-Mellon University
    ## 584                        PHD 2001 McGill University
    ## 585               MACC 2020 Univ of Wisconsin-Madison
    ## 586                      PHD 2011 Stanford University
    ## 587               PHD 1993 Scuola Normale Sup de Pisa
    ## 588                                             PHD  
    ## 589           PHD 2010 Univ of Arkansas, Fayetteville
    ## 590                    PHD 2006 University of Arizona
    ## 591                  PHD 2007 Northwestern University
    ## 592                DVM 2000 Univ of Wisconsin-Madison
    ## 593            PHD 1998 U of California-Santa Barbara
    ## 594                MFA 1983 Rutgers State Univ-Newark
    ## 595             PHD 2014 Univ of California San Diego
    ## 596                  PHD 1983 Northwestern University
    ## 597                 MS 2003 Univ of Wisconsin-Madison
    ## 598                MSW 2005 Univ of Wisconsin-Madison
    ## 599                       PHD 2006 University of Iowa
    ## 600                    PHD 2018 University of Georgia
    ## 601                PHD 2015 Univ of Wisconsin-Madison
    ## 602                  PHD 1989 Kansas State University
    ## 603               PHS  Univ of IL at Urbana-Champaign
    ## 604                 PHD 2009 Arizona State University
    ## 605                          PHD 1997 Yale University
    ## 606                           MS 2006 Ohio University
    ## 607                       PHD 2015 University of Iowa
    ## 608              PHD 2018 Univ of Wisconsin-Milwaukee
    ## 609                       PHD 2013 Cornell University
    ## 610             MBA 2005 Univ of Wisconsin-Whitewater
    ## 611            PHD 2001 Univ of Minnesota-Twin Cities
    ## 612              MD 2007 Medical College Of Wisconsin
    ## 613                 PHD 1976 Brooklyn College Of Cuny
    ## 614                       PHD  Universitat Dusseldorf
    ## 615           PHD 1993 Univ of California Los Angeles
    ## 616                    PHD 1994 University of Vermont
    ## 617                 JD 1980 Univ of Wisconsin-Madison
    ## 618            MA 1990 California State U- Long Beach
    ## 619               MS 2007 Rochester Institute Of Tech
    ## 620               PHD 2011 University of Pennsylvania
    ## 621                      PHD 2002 Stanford University
    ## 622              MSN 2013 Cardinal Stritch University
    ## 623                       PHD 2008 Cornell University
    ## 624                    PHD 1981 University of Florida
    ## 625                 JD 2005 Univ of Wisconsin-Madison
    ## 626                    PHD 1975 University of Georgia
    ## 627                 JD 1995 Univ of Wisconsin-Madison
    ## 628                PHD 1998 Univ of Wisconsin-Madison
    ## 629                PHD 2012 Univ of Wisconsin-Madison
    ## 630                PHD 2000 Univ of Wisconsin-Madison
    ## 631                  PHD 2007 Texas Womans University
    ## 632                PHD 1985 Univ of Wisconsin-Madison
    ## 633                PHD 2015 Univ of Wisconsin-Madison
    ## 634                PHD 2001 Univ of Wisconsin-Madison
    ## 635               MSSW 2003 Univ of Wisconsin-Madison
    ## 636                 MS 1994 Univ of Wisconsin-Madison
    ## 637                PHD 1997 Univ of Wisconsin-Madison
    ## 638            PHD 1975 Univ of Michigan at Ann Arbor
    ## 639                     MFA 2017 University of London
    ## 640                PHD 2014 Colorado State University
    ## 641            PHD 2008 U of California-Santa Barbara
    ## 642           PHD 1999 Univ of California Los Angeles
    ## 643                  PHD 2017 Northwestern University
    ## 644                    PHD 1998 University of Georgia
    ## 645                    DVM 1992 University of Bristol
    ## 646            PHD 1985 Univ of Michigan at Ann Arbor
    ## 647                PHD 1993 Univ of Wisconsin-Madison
    ## 648                    PHD 2002 University of Florida
    ## 649                    PHD 2017 University of Georgia
    ## 650                      PHD 2003 Columbia University
    ## 651            MSW 1991 Univ of Michigan at Ann Arbor
    ## 652                       PHD 2005 Harvard University
    ## 653                                          MS 2016 
    ## 654                       PHD 1983 Cornell University
    ## 655                          PHD 1990 Yale University
    ## 656           MFA 2007 Univ of IL at Urbana-Champaign
    ## 657                                         PHD 2018 
    ## 658            PHD 1982 Univ of Michigan at Ann Arbor
    ## 659                     JD  Univ of Wisconsin-Madison
    ## 660                       PHD 2006 University of Iowa
    ## 661               PHD 2011 Case Western Reserve Univ.
    ## 662            PHD 2014 Pennsylvania State University
    ## 663            PHD 2008 Univ of Minnesota-Twin Cities
    ## 664            PHD 1978 Pennsylvania State University
    ## 665                 MS 2018 Univ of Wisconsin-Madison
    ## 666           PHD 1998 Calif. State Univ. Los Angeles
    ## 667              MD 2008 Loyola University of Chicago
    ## 668                      PHD 1980 Brandeis University
    ## 669           PHD 1989 Australian National University
    ## 670            PHD 2015 U of California San Francisco
    ## 671                 JD 1995 Univ of Wisconsin-Madison
    ## 672                       MS 1996 Stanford University
    ## 673                    PHD 2002 Ohio State University
    ## 674                    PHD 1972 Washington University
    ## 675           AUD 2017 Univ of Wisconsin-StevensPoint
    ## 676                       PHD 2017 Harvard University
    ## 677            PHD 2000 Univ of Michigan at Ann Arbor
    ## 678                PHD 1984 Colorado State University
    ## 679                PHD 1996 Univ of Wisconsin-Madison
    ## 680                                         PHD 2011 
    ## 681           PHD 1980 University of Nebraska-Lincoln
    ## 682            EDD 2006 Pennsylvania State University
    ## 683            PHD 1998 Univ of Minnesota-Twin Cities
    ## 684                          PHD 1990 Yale University
    ## 685                     PHD 1991 Princeton University
    ## 686               MS 1983 Rensselaer Polytechnic Inst
    ## 687                 MA 2013 Univ of Wisconsin-Madison
    ## 688                 PHD 1987 University of Pittsburgh
    ## 689                        MD 1987 Harvard University
    ## 690                PHD 2006 Univ of Wisconsin-Madison
    ## 691                PHD 1989 Michigan State University
    ## 692                  DVM 2000 Kansas State University
    ## 693                PHD 1999 Univ of Wisconsin-Madison
    ## 694           PHD 1999 Univ Joseph Fourier Grenoble I
    ## 695                    PHD 2000 University of Toronto
    ## 696                  DMA 2015 Northwestern University
    ## 697                 PHD 2000 Florida State University
    ## 698                 PHD 2003 University of Washington
    ## 699                 MS 2010 Univ of Wisconsin-Madison
    ## 700            PHD 1987 SUNY Health Sci Cntr-Brooklyn
    ## 701                PHD 1980 Univ of Wisconsin-Madison
    ## 702             MS 2003 Univ of Minnesota-Twin Cities
    ## 703                                              ME  
    ## 704                        PHD 2000 Tulane University
    ## 705                PHD 1998 Univ of Wisconsin-Madison
    ## 706                 PHD 1990 Johns Hopkins University
    ## 707                PHD 2005 North Carolina State Univ
    ## 708                         PHD 1995 Brown University
    ## 709                                  PHD 1998 Hungary
    ## 710               PHD 2015 University of Pennsylvania
    ## 711                  PHD 1988 University Of Rochester
    ## 712                       PHD 1976 Harvard University
    ## 713                            MS  UW Colleges Online
    ## 714                    PHD 2001 University of Chicago
    ## 715           PHD 1995 Univ of California Los Angeles
    ## 716                PHD 1987 Univ of Wisconsin-Madison
    ## 717                 JD 2002 Univ of Wisconsin-Madison
    ## 718                      PHD 2014 New York University
    ## 719            PHD 2006 Univ of Maryland College Park
    ## 720                       PHD 2008 Cornell University
    ## 721                      PHD 2000 Columbia University
    ## 722              DVM 2008 Univ Federal de Santa Maria
    ## 723                PHD 2002 Univ of Wisconsin-Madison
    ## 724               PHD 1993 Potchefstroomse University
    ## 725                PHD 1970 Univ of Wisconsin-Madison
    ## 726                 JD 1975 Univ of Wisconsin-Madison
    ## 727                             PHD  Brown University
    ## 728                MBA 2009 Univ of Wisconsin-Madison
    ## 729              PHD 1984 Univ of California Berkeley
    ## 730                 DVM 1981 Univ of California Davis
    ## 731                     MD 1980 University of Florida
    ## 732                PHD 2009 Univ of Wisconsin-Madison
    ## 733                      PHD 1992 Stanford University
    ## 734                PHD 1994 Univ of Wisconsin-Madison
    ## 735               PHD 2009 Univ degli Studi di Padova
    ## 736                 MS 2001 Univ of Wisconsin-Madison
    ## 737           PHD 2000 Univ of California Los Angeles
    ## 738           PHD 1988 Univ of IL at Urbana-Champaign
    ## 739                  MS 1991 West Virginia University
    ## 740                PHD 1955 Univ of Wisconsin-Madison
    ## 741              PHD 1984 Univ of California Berkeley
    ## 742                  PHD 1988 Northwestern University
    ## 743            PHD 1970 Univ of Minnesota-Twin Cities
    ## 744                 MD 2007 Univ of Wisconsin-Madison
    ## 745                    PHD 2008 Texas Tech University
    ## 746                     MD 1977 University of Chicago
    ## 747             MD 1989 Univ of Michigan at Ann Arbor
    ## 748                PHD 1989 Univ of Wisconsin-Madison
    ## 749                PHD 1983 Univ of Wisconsin-Madison
    ## 750                    PHD 2016 University of Wyoming
    ## 751                                             PHD  
    ## 752              PHD 1999 Moscow State Univ Lomonosov
    ## 753            PHD 2000 Pennsylvania State University
    ## 754            PHD 2004 Univ of Minnesota-Twin Cities
    ## 755                                          BS 1985 
    ## 756                PHD 2001 Univ of Wisconsin-Madison
    ## 757               PHD 1993 Texas A &amp; M University
    ## 758                 MS 2000 Univ of Wisconsin-Madison
    ## 759            PHD 2006 Pennsylvania State University
    ## 760               JD 1994 Univ of California Berkeley
    ## 761              PHD 1985 Univ of California Berkeley
    ## 762                                         PHD 2018 
    ## 763                     PHD 2000 Princeton University
    ## 764                      PHD 2015 Columbia University
    ## 765                    PHD 1985 Ohio State University
    ## 766                                         MMS 2000 
    ## 767                 DS 2009 ROCKY MOUNTAIN UNIVERSITY
    ## 768              PHD 2006 Univ of California Berkeley
    ## 769                MD 2007 Baylor College Of Medicine
    ## 770            PHD 1990 Pennsylvania State University
    ## 771                    PHD 1989 University of Chicago
    ## 772                      PHD 2011 Columbia University
    ## 773                      PHD 2016 Columbia University
    ## 774              MD 1985 U Health Sci/Chicago Med Sch
    ## 775                  PHD 1998 Northwestern University
    ## 776                    DVM 2011 Universidade do Porto
    ## 777                 PHD 2003 University of Washington
    ## 778                         PHD  Princeton University
    ## 779                MSW 2014 Univ of Wisconsin-Madison
    ## 780                PHD 1997 Univ of Wisconsin-Madison
    ## 781                PHD 1991 Univ of California Irvine
    ## 782                PHD 2009 Univ of Wisconsin-Madison
    ## 783                     PHD 1988 Princeton University
    ## 784            PHD 1994 Univ of Alabama at Birmingham
    ## 785                PHD 2001 Rutgers State Univ-Newark
    ## 786            PHD 2010 Univ of Minnesota-Twin Cities
    ## 787                            BA 1998 Univ Of Da Lat
    ## 788                             PHD  Universitat Wien
    ## 789               MS 2012 Rensselaer Polytechnic Inst
    ## 790                        MS 1988 Harvard University
    ## 791                       PHD 2016 Cornell University
    ## 792            PHD 2000 Univ of Michigan at Ann Arbor
    ## 793                 PHD 2002 University of Washington
    ## 794                  PHD 2005 Northwestern University
    ## 795                  PHD 2005 University of St Thomas
    ## 796                PHD 1980 Univ of Wisconsin-Madison
    ## 797             PHD 2002 U of South Carolina-Columbia
    ## 798                 MM 1984 University of Connecticut
    ## 799                      PHD 1984 University Of Miami
    ## 800                PHD 2005 Michigan State University
    ## 801                  PHD 2003 Kansas State University
    ## 802               MFA 1988 Virginia Commonwealth Univ
    ## 803               PHD 2003 Univ degli Studi di Milano
    ## 804                                         DVM 2014 
    ## 805            PHD 1980 Pennsylvania State University
    ## 806               DVM 1992 Justus Liebig Univ Giessen
    ## 807             PHARMD 1999 Univ of Wisconsin-Madison
    ## 808                        PHD 1987 Temple University
    ## 809                   MD 2002 Northwestern University
    ## 810            DVM 2013 Louisiana State U-Baton Rouge
    ## 811                AUD 2006 Univ of Wisconsin-Madison
    ## 812                      PHD 2008 New York University
    ## 813                 PHD 2000 Johns Hopkins University
    ## 814                        JD 1972 Harvard University
    ## 815                PHD 2000 North Carolina State Univ
    ## 816               MS 2007 University of New Hampshire
    ## 817            PHD 1994 Univ of Michigan at Ann Arbor
    ## 818                 PHD 2009 University of Washington
    ## 819                PHD 2018 Univ of Wisconsin-Madison
    ## 820                      PHD 1973 Columbia University
    ## 821                PHD 2017 Univ of Wisconsin-Madison
    ## 822              PHD 2011 Univ of Illinois at Chicago
    ## 823        PHD 2008 Iowa State Univ of Sci &amp; Tech
    ## 824               PHD 1990 University of Pennsylvania
    ## 825                       PHD 1977 University of Iowa
    ## 826                 MS 1993 Univ of Wisconsin-Madison
    ## 827                 MD 2013 Univ of Wisconsin-Madison
    ## 828              PHD 2014 Univ of Illinois at Chicago
    ## 829                      PHD 1974 Stanford University
    ## 830                    PHD 1975 University of Glasgow
    ## 831                DPT 2016 College Of St Scholastica
    ## 832            PHD 2007 Pennsylvania State University
    ## 833           PHD 1975 Univ of IL at Urbana-Champaign
    ## 834                        MSW 2011 Aurora University
    ## 835                        MSW 2009 Aurora University
    ## 836                       PHD 1999 Harvard University
    ## 837                PHD 1982 Univ of Wisconsin-Madison
    ## 838                    PHD 2007 University of Florida
    ## 839                DVM 2011 Univ of Wisconsin-Madison
    ## 840            PHD 2003 Univ of Michigan at Ann Arbor
    ## 841              PHD 2014 Univ of Wisconsin-Milwaukee
    ## 842                PHD 2004 Univ of Wisconsin-Madison
    ## 843                 JD 1965 Univ of Wisconsin-Madison
    ## 844                    PHD 2007 University of Chicago
    ## 845                PHD 2015 Univ of Wisconsin-Madison
    ## 846                      AA 1983 University of London
    ## 847                PHD 2006 Univ of Wisconsin-Madison
    ## 848                                   PHD 2014 Canada
    ## 849                 MS 2004 Univ of Wisconsin-Madison
    ## 850                                         DVM 2006 
    ## 851         PHARMD 1983 University of Texas at Austin
    ## 852            PHD 2003 Univ of Maryland College Park
    ## 853                     MD 1999 Georgetown University
    ## 854                                            DRPH  
    ## 855               MSSW 2001 Univ of Wisconsin-Madison
    ## 856                PHD 1983 Univ of Wisconsin-Madison
    ## 857                      PHD 1984 Stanford University
    ## 858                        BA 2011 Cornell University
    ## 859                          PHD 2016 Duke University
    ## 860                 BS 2000 Univ of Wisconsin-Madison
    ## 861                    PHD 1980 Washington University
    ## 862                 MS 1997 Univ of Wisconsin-Madison
    ## 863                       PHD 2017 Indiana University
    ## 864               PHD 2018 Massachusetts Inst Of Tech
    ## 865                    JD 1989 Wayne State University
    ## 866                MSW 2013 Univ of Wisconsin-Madison
    ## 867                       PHD 1999 Harvard University
    ## 868                     PHD 1998 University of Oxford
    ## 869              JD 1987 George Washington University
    ## 870                 MD 2002 Univ of Wisconsin-Madison
    ## 871             MD 1986 Univ of Massachusetts Med Sch
    ## 872                         PHD 2013 Emory University
    ## 873                     MD 1968 University of Chicago
    ## 874                PHD 1987 Univ of Wisconsin-Madison
    ## 875                EDM 1996 Univ of Wisconsin-Madison
    ## 876                PHD 1985 Univ of Wisconsin-Madison
    ## 877                 MS 2000 Univ of Wisconsin-Madison
    ## 878                                         DVM 2016 
    ## 879            PHD 2011 U of California-Santa Barbara
    ## 880                   PHD 2000 University of Montreal
    ## 881                    PHD 2012 University of Chicago
    ## 882                  MD 1986 University Of New Mexico
    ## 883                       MSW 2015 University of Iowa
    ## 884                                         PHD 2014 
    ## 885                PHD 2016 Univ of Wisconsin-Madison
    ## 886                   PHD 2019 University of Virginia
    ## 887                       PHD 1998 Harvard University
    ## 888            M.P.AFF 2003 Univ of Wisconsin-Madison
    ## 889                       PHD 1981 Indiana University
    ## 890                         MFA 2007 Columbia College
    ## 891                PHD 2017 Univ of Wisconsin-Madison
    ## 892                PHD 2015 Univ of Wisconsin-Madison
    ## 893                 PHD 2012 Univ of California Davis
    ## 894                DVM 2013 Univ of Wisconsin-Madison
    ## 895                       PHD 2006 Harvard University
    ## 896              PHD 1993 Universidad de Buenos Aires
    ## 897                       PHD 1989 Harvard University
    ## 898                       PHD 1999 Cornell University
    ## 899              PHD 2011 Washington State University
    ## 900                      BS 1983 Princeton University
    ## 901                DNP 2013 Univ of Wisconsin-Madison
    ## 902            DM 2020 Univ of IL at Urbana-Champaign
    ## 903              PHD 1983 Univ of California Berkeley
    ## 904               PHD 2006 Univ of Colorado at Denver
    ## 905                 PHD 2010 Johns Hopkins University
    ## 906               PHD 2007 Baylor College Of Medicine
    ## 907              PHD 2011 Univ of California Berkeley
    ## 908                PHD 2011 Univ of Wisconsin-Madison
    ## 909            PHD 1999 Univ of Minnesota-Twin Cities
    ## 910            PHD 1976 Univ of Minnesota-Twin Cities
    ## 911                    PHD 2014 University of Chicago
    ## 912                       PHD 2012 Cornell University
    ## 913            PHD 1993 Univ of Minnesota-Twin Cities
    ## 914                      PHD 1991 Stanford University
    ## 915           PHD 2008 University of Nebraska-Lincoln
    ## 916          MACC 2001 University of Nebraska-Lincoln
    ## 917                    PHD  Univ of Wisconsin-Madison
    ## 918                    PHD 2001 University of Chicago
    ## 919                PHD 2018 Univ of Wisconsin-Madison
    ## 920                       PHD 1997 Harvard University
    ## 921           PHD 2011 Univ of IL at Urbana-Champaign
    ## 922                 MS 2018 Univ of Wisconsin-Madison
    ## 923              PHD 1971 Univ of California Berkeley
    ## 924                    PHD 1997 University of Chicago
    ## 925              PHD 2010 Univ of California Berkeley
    ## 926                       PHD 2008 University of Iowa
    ## 927                      PHD 2000 Syracuse University
    ## 928              MA 1980 Indiana Univ Of Pennsylvania
    ## 929            DO 2013 Philadelphia Colg of Osteopath
    ## 930                PHD 2012 Univ of Wisconsin-Madison
    ## 931              PHD 1983 Univ of California Berkeley
    ## 932              PHD 1993 Univ of California Berkeley
    ## 933                PHD 1997 Univ of Wisconsin-Madison
    ## 934                 MA 1998 Univ of Wisconsin-Madison
    ## 935                       PHD 2000 Harvard University
    ## 936            PHD 1996 Univ of Michigan at Ann Arbor
    ## 937                 MD 1995 Univ of Wisconsin-Madison
    ## 938               PHD 1998 University of Pennsylvania
    ## 939                 PHD 1984 Eotvos Lorand University
    ## 940                PHD 1975 Univ of Wisconsin-Madison
    ## 941                     MA 2006 University of Chicago
    ## 942                          PHD 2000 Mayo Foundation
    ## 943                     JD  Univ of Wisconsin-Madison
    ## 944                 JD 1997 Univ of Wisconsin-Madison
    ## 945                        MD 2000 University of Iowa
    ## 946                     PHD 2014 Princeton University
    ## 947                        MFA 1991 Boston University
    ## 948                                             PHD  
    ## 949                    PHD 2015 University of Chicago
    ## 950                    MD 1992 Beirut Arab University
    ## 951              PHD 1995 Univ of Illinois at Chicago
    ## 952                         PHD 2017 University of MI
    ## 953             PHD 2012 George Washington University
    ## 954               PHD 2020 Texas A &amp; M University
    ## 955                PHD 1988 Univ of Wisconsin-Madison
    ## 956               PHD 1991 Massachusetts Inst Of Tech
    ## 957                      PHD 2008 Stanford University
    ## 958              PHD 1994 Univ of California Berkeley
    ## 959                       MD 1996 SUNY At Stony Brook
    ## 960                PHD 2007 Univ of Wisconsin-Madison
    ## 961               PHD 2015 Texas A &amp; M University
    ## 962            PHD 2020 Univ of Maryland College Park
    ## 963               MSSW 1984 Univ of Wisconsin-Madison
    ## 964            PHD 2017 Univ of Michigan at Ann Arbor
    ## 965              PHD 1987 Univ of Colorado at Boulder
    ## 966                PHD 2015 Univ of Wisconsin-Madison
    ## 967                       PHD 1976 Harvard University
    ## 968                  DVM 2005 Univ Federal Fluminense
    ## 969              PHD 2009 Univ of California Berkeley
    ## 970                  PHD 1988 University of Cambridge
    ## 971                DNP 2012 Univ of Wisconsin-Madison
    ## 972                 BS 2005 Univ of Wisconsin-Madison
    ## 973                       PHD 2012 Cornell University
    ## 974                PHD 2017 Colorado State University
    ## 975                                             PHD  
    ## 976                           JD 1985 Yale University
    ## 977                       JD 2009 Stanford University
    ## 978                PHD 2016 Univ of Wisconsin-Madison
    ## 979                PHD 2009 Univ of Wisconsin-Madison
    ## 980                PHD 2015 Univ of Wisconsin-Madison
    ## 981                PHD 1989 Univ of Wisconsin-Madison
    ## 982             MA 1982 New England Cnsrvtry Of Music
    ## 983         PHARMD 1993 Univ of Minnesota-Twin Cities
    ## 984                PHD 1998 Univ of Wisconsin-Madison
    ## 985                MSW 1989 Univ of Wisconsin-Madison
    ## 986                  MD 2014 University Of New Mexico
    ## 987           MFA 2005 Univ of California Los Angeles
    ## 988            PHD 1987 Univ of Michigan at Ann Arbor
    ## 989                MFA 1988 Univ of Wisconsin-Madison
    ## 990                    PHD 2012 University of Toronto
    ## 991                PHD 2006 Univ of Wisconsin-Madison
    ## 992            MS 2017 Univ of IL at Urbana-Champaign
    ## 993                  PHD 2007 Northwestern University
    ## 994                PHD 1998 Univ of Wisconsin-Madison
    ## 995                PHD 1978 Univ of Wisconsin-Madison
    ## 996                    PHD 2010 Ohio State University
    ## 997                PHD 2004 Univ of Wisconsin-Madison
    ## 998                     PHD 1992 Princeton University
    ## 999                     PHD 1993 Princeton University
    ## 1000              DVM 1988 University of Pennsylvania
    ## 1001                  MS 1999 Northwestern University
    ## 1002                          MD 1964 Yale University
    ## 1003               PHD 2005 Univ of Wisconsin-Madison
    ## 1004                 PHD 1980 Northwestern University
    ## 1005                         JD 2003 Emory University
    ## 1006           PHD 1989 Univ of Minnesota-Twin Cities
    ## 1007               PHD 1992 Univ of Wisconsin-Madison
    ## 1008            PHD 1998 Loyola University of Chicago
    ## 1009                    MS 1986 Ohio State University
    ## 1010                      MS 1993 Stanford University
    ## 1011                  MD 2004 University Of Rochester
    ## 1012                                        PHD 2008 
    ## 1013            PHD 2009 California Institute of Tech
    ## 1014               DNP 2016 Univ of Wisconsin-Madison
    ## 1015                MS 2014 Univ of Wisconsin-Madison
    ## 1016                 MSW 2005 College Of St Catherine
    ## 1017               MPA 2008 Univ of Wisconsin-Madison
    ## 1018               DVM 2017 Univ of Wisconsin-Madison
    ## 1019              PHD 1999 Georgia Inst of Technology
    ## 1020               PHD 2009 Univ of Wisconsin-Madison
    ## 1021                      PHD 2005 Cornell University
    ## 1022            PHD 2012 Rutgers St Unv-New Brunswick
    ## 1023             PHD 1994 Univ of California Berkeley
    ## 1024                                        MPA 2012 
    ## 1025                        MS 2011 DePaul University
    ## 1026           PHD 1996 North Dakota State University
    ## 1027                     PHD 1985 Brandeis University
    ## 1028                JD 1992 Univ of Wisconsin-Madison
    ## 1029               PHD 2015 Univ of Wisconsin-Madison
    ## 1030               PHD 1973 Univ of Wisconsin-Madison
    ## 1031               PHD 2003 Univ of Wisconsin-Madison
    ## 1032               DVM 1991 Univ of Wisconsin-Madison
    ## 1033               PHD 1983 Univ of Wisconsin-Madison
    ## 1034               PHD 1991 Univ of Wisconsin-Madison
    ## 1035              PSYD 2017 Univ of Wisconsin-Madison
    ## 1036              PHD 2010 University of Pennsylvania
    ## 1037              PHD 2017 Texas A &amp; M University
    ## 1038              MACC 2000 Univ of Wisconsin-Madison
    ## 1039             PHD 1986 Univ of California Berkeley
    ## 1040            MA 1976 New England Cnsrvtry Of Music
    ## 1041               MS 1977 Massachusetts Inst Of Tech
    ## 1042             MD 2005 Loyola University of Chicago
    ## 1043                          MS 2012 Bentley College
    ## 1044           MFA 1982 University of Hawaii at Manoa
    ## 1045               EDM 2019 Univ of Wisconsin-Madison
    ## 1046                   PHD 2019 Ohio State University
    ## 1047                         PHD 2014 Yale University
    ## 1048                   PHD 1999 University of Chicago
    ## 1049                   PHD 2011 University of Arizona
    ## 1050               MSN 2011 Univ of Wisconsin-Oshkosh
    ## 1051                   MD 1988 University of Montreal
    ## 1052               MD 1993 Univ of Colorado at Denver
    ## 1053            PHARMD 2005 Univ of Wisconsin-Madison
    ## 1054                 PHD  Washington State University
    ## 1055              PHD 2010 Univ degli Studi di Milano
    ## 1056                  MD 1983 Univ Federal de Pelotas
    ## 1057           PHD 1998 Univ of Michigan at Ann Arbor
    ## 1058                PHD 1997 University of Washington
    ## 1059          PHD 2010 Univ of IL at Urbana-Champaign
    ## 1060           PHD 2001 Univ of Minnesota-Twin Cities
    ## 1061               PHD 1998 Univ of Wisconsin-Madison
    ## 1062                                          OQUAL  
    ## 1063           PHD 2017 U of California-Santa Barbara
    ## 1064             PHD 2010 Univ of California Berkeley
    ## 1065          PHD 2010 University of Nebraska-Lincoln
    ## 1066              PHD 2015 Carnegie-Mellon University
    ## 1067               MSW 2010 Univ of Wisconsin-Madison
    ## 1068                    PHD 2017 Princeton University
    ## 1069                PHD 2009 Johns Hopkins University
    ## 1070                PHD 2015 St. Catherine University
    ## 1071               PHD 2003 Univ of Wisconsin-Madison
    ## 1072                     PHD 2000 Stanford University
    ## 1073                                        PHD 2015 
    ## 1074               PHD 2014 Univ of Wisconsin-Madison
    ## 1075              MS 1986 Washington State University
    ## 1076                                         M.ARCH  
    ## 1077                BA 2012 Univ of Wisconsin-Madison
    ## 1078                      PHD 2002 Cornell University
    ## 1079               PHD  U of California-Santa Barbara
    ## 1080                PHD  Ludwig Maximilians U Munchen
    ## 1081                     PHD 1986 Columbia University
    ## 1082               MA 2001 Univ of Colorado at Denver
    ## 1083               PHD 2001 Univ of Wisconsin-Madison
    ## 1084                PHD 2011 Arizona State University
    ## 1085          MFA 1984 Sch Of The Art Inst Of Chicago
    ## 1086                         PHD 2017 SUNY at Buffalo
    ## 1087                MS 2006 Univ of Wisconsin-Madison
    ## 1088                   PHD 2017 Washington University
    ## 1089             PHD 1995 Univ of California Berkeley
    ## 1090               PHD 1985 Univ of Wisconsin-Madison
    ## 1091              MD 1981 University of South Florida
    ## 1092           PHD 1983 University of Texas at Austin
    ## 1093               PHD 2005 Michigan State University
    ## 1094                     PHD 2001 Columbia University
    ## 1095                    PHD 1995 Princeton University
    ## 1096           PHD 2008 Univ of Michigan at Ann Arbor
    ## 1097               PHD 2008 Univ of Wisconsin-Madison
    ## 1098               PHD 1989 Univ of Wisconsin-Madison
    ## 1099                        PHD 2018 University of MI
    ## 1100             PHARMD 1990 University of Washington
    ## 1101                     PHD 1993 Columbia University
    ## 1102          PHD 1987 Univ Studi di Roma-La Sapienza
    ## 1103                      MS 1989 Stanford University
    ## 1104               PHD 1999 Univ of Wisconsin-Madison
    ## 1105    PHD 2001 Louisiana State U &amp; A&amp;M Colg
    ## 1106                         PHD 2010 Yale University
    ## 1107                      PHD 1991 Indiana University
    ## 1108                 PHD 1987 University of Edinburgh
    ## 1109                     PHD 2006 Stanford University
    ## 1110                         PHD 2011 Nova University
    ## 1111                   MLIS 2009 Dominican University
    ## 1112             PHD 2011 Univ of California Berkeley
    ## 1113              PHD 2012 Carnegie-Mellon University
    ## 1114                    PHD 1976 Princeton University
    ## 1115          DMA 1999 Univ of IL at Urbana-Champaign
    ## 1116               MSW 2014 Univ Of Minnesota-St Paul
    ## 1117                   PHD  Univ Of NC At Chapel Hill
    ## 1118              JD 2004 Chicago-Kent College Of Law
    ## 1119              PHD 1994 Carnegie-Mellon University
    ## 1120                JD 2007 Univ of Wisconsin-Madison
    ## 1121                MS 2011 Univ of Wisconsin-Madison
    ## 1122                PHD 1993 Arizona State University
    ## 1123                PHD 2016 Johns Hopkins University
    ## 1124            PHD 2009 Eurasian National University
    ## 1125             PHD 2010 Russian Academy of Sciences
    ## 1126           PHD 2005 Univ of Michigan at Ann Arbor
    ## 1127               MFA 2008 Univ of Wisconsin-Madison
    ## 1128                MS 2004 Univ of Wisconsin-Madison
    ## 1129                   PHD 2012 Vanderbilt University
    ## 1130                      PHD 2019 Cornell University
    ## 1131                    PHD 2017 Princeton University
    ## 1132                  PHD 2001 New College of Florida
    ## 1133              PSYD 2017 Univ of Wisconsin-Madison
    ## 1134                      PHD 1996 Harvard University
    ## 1135                          MD 2004 Yale University
    ## 1136                    PHD 2002 University of Kansas
    ## 1137             PHD 2009 Univ of California Berkeley
    ## 1138               PHD 1991 Univ of Wisconsin-Madison
    ## 1139           PHD 1978 Univ of Minnesota-Twin Cities
    ## 1140                 PHD 2007 Northwestern University
    ## 1141             PHD 2015 Univ of California Berkeley
    ## 1142          PHD 1984 Univ of IL at Urbana-Champaign
    ## 1143               PHD 1985 Univ of Wisconsin-Madison
    ## 1144                       PHD  Vanderbilt University
    ## 1145           PHD 1995 Univ of Minnesota-Twin Cities
    ## 1146                      MD 2007 Columbia University
    ## 1147           PHD 1999 Univ of Michigan at Ann Arbor
    ## 1148                   PHD 1994 University of Chicago
    ## 1149                MM 2014 Univ of Wisconsin-Madison
    ## 1150               PHD 2011 Univ of Wisconsin-Madison
    ## 1151           PHD 1996 Univ of Minnesota-Twin Cities
    ## 1152                    PHD 1981 Princeton University
    ## 1153             PHD 1988 Univ of California Berkeley
    ## 1154                      PHD 2001 Cornell University
    ## 1155             PHD 2011 Moscow State Univ Lomonosov
    ## 1156          MBA 1997 University of Alaska-Anchorage
    ## 1157                      PHD 1988 Cornell University
    ## 1158                MD 2000 Univ of Wisconsin-Madison
    ## 1159                        PHD 1980 Brown University
    ## 1160                MM 1989 Manhattan School Of Music
    ## 1161               PHD 1987 Univ of Wisconsin-Madison
    ## 1162           PHD 1975 Univ of Michigan at Ann Arbor
    ## 1163                      PHD 1991 Cornell University
    ## 1164                       PHD 2009 Auburn University
    ## 1165           PHD 2010 U of California-Santa Barbara
    ## 1166               MFA 1980 SUNY College at New Paltz
    ## 1167                BS 2007 Univ of Wisconsin-Madison
    ## 1168               DVM 2017 Univ of Wisconsin-Madison
    ## 1169               PHD 1972 Univ of Wisconsin-Madison
    ## 1170              PHD 2009 University of Pennsylvania
    ## 1171               PHD 2017 Univ of Wisconsin-Madison
    ## 1172                                        PHD 2008 
    ## 1173             PHD 1997 Univ of California Berkeley
    ## 1174             PHD 1990 Univ of Colorado at Boulder
    ## 1175                     PHD 2013 Columbia University
    ## 1176                PHD 2018 Florida State University
    ## 1177                    PHD 2003 University of London
    ## 1178          MFA 1985 Univ of IL at Urbana-Champaign
    ## 1179                 PHD 2008 University Of Rochester
    ## 1180                    MS  Univ of Wisconsin-Madison
    ## 1181               PHD 2007 Univ Of NC At Chapel Hill
    ## 1182           PHD 2004 Pennsylvania State University
    ## 1183                         PHD 1996 Duke University
    ## 1184              JD 1974 Univ of California Berkeley
    ## 1185              DNS 2017 University of Pennsylvania
    ## 1186               MSW 2010 Univ of Wisconsin-Madison
    ## 1187               PHD 2002 Univ of Wisconsin-Madison
    ## 1188           PHD 2012 Univ of Michigan at Ann Arbor
    ## 1189                 PHD 1991 University Of Rochester
    ## 1190               PHD 1985 Univ of Wisconsin-Madison
    ## 1191                   PHD 2014 University of Georgia
    ## 1192               MS 2007 Texas A &amp; M University
    ## 1193                       MFA 2004 Alfred University
    ## 1194                      PHD 1993 Harvard University
    ## 1195           PHD 2014 University of Texas at Austin
    ## 1196             PHD 2006 City University Of New York
    ## 1197                PHD 1991 East Carolina University
    ## 1198               PHD 2002 Univ of Wisconsin-Madison
    ## 1199                                        PHD 2014 
    ## 1200                       JD 1999 Hofstra University
    ## 1201               MSW 2010 Univ of Wisconsin-Madison
    ## 1202           PHD 1991 U of California-Santa Barbara
    ## 1203                           PHD 1996 Texas College
    ## 1204               PHD 2001 North Carolina State Univ
    ## 1205                PHD 1993 Johns Hopkins University
    ## 1206               LLM 2005 Univ of Wisconsin-Madison
    ## 1207           PHD 1988 Univ of Maryland College Park
    ## 1208                   PHD 2004 Utah State University
    ## 1209                PHD  Medical College Of Wisconsin
    ## 1210                    MA 2014 University of Montana
    ## 1211                     PHD 1996 Stanford University
    ## 1212          PHD 1985 Univ of IL at Urbana-Champaign
    ## 1213                BA 1989 Univ of Wisconsin-Madison
    ## 1214                        PHD 2015 Universitat Bonn
    ## 1215           PHD 2004 China Agricultural University
    ## 1216           PHD 2012 Univ of Minnesota-Twin Cities
    ## 1217              PHD 2011 Carnegie-Mellon University
    ## 1218                 JD 2011 University of Pittsburgh
    ## 1219                     PHD 2005 Tel Aviv University
    ## 1220                MS 2010 Univ of Wisconsin-Madison
    ## 1221                MD 2012 Univ of Wisconsin-Madison
    ## 1222                DS 2016 University of New Orleans
    ## 1223       PHD 2008 Iowa State Univ of Sci &amp; Tech
    ## 1224             PHD 2001 Univ of California Berkeley
    ## 1225            PHARMD 2012 Univ of Wisconsin-Madison
    ## 1226                                            MBA  
    ## 1227                                        DVM 2009 
    ## 1228                MS 1992 Naval Postgraduate School
    ## 1229                MS 2011 Univ of Wisconsin-Madison
    ## 1230                      PHD 2007 Cornell University
    ## 1231               MFA 2009 Univ of Wisconsin-Madison
    ## 1232               MLA 2011 Univ of Wisconsin-Madison
    ## 1233           MD 1970 Ferdowsi University of Mashhad
    ## 1234            PHARMD 2005 Univ of Wisconsin-Madison
    ## 1235           MFA 2011 Univ of Massachusetts Amherst
    ## 1236               PHD 2016 Univ of Wisconsin-Madison
    ## 1237                 PHD 1998 Northwestern University
    ## 1238                JD 1994 Univ of Wisconsin-Madison
    ## 1239              PHD  Hebrew University of Jerusalem
    ## 1240                     MFA 2018 Columbia University
    ## 1241                    MS 1985 University of Arizona
    ## 1242               PHD 1994 Michigan State University
    ## 1243              PHD 2011 Baylor College Of Medicine
    ## 1244                       BA 1981 Indiana University
    ## 1245               PHD 1999 Univ of Wisconsin-Madison
    ## 1246               PHD 2007 Univ Of NC At Chapel Hill
    ## 1247               PHD 1988 Univ of Wisconsin-Madison
    ## 1248                       DS 2011 Andrews University
    ## 1249               PHD 1994 Univ of Wisconsin-Madison
    ## 1250             DNP 2011 Univ of Wisconsin-Milwaukee
    ## 1251                      PHD 2009 Harvard University
    ## 1252               PHD 2006 Univ of Wisconsin-Madison
    ## 1253                 PHD 2005 Northwestern University
    ## 1254                 PHD 2001 Northwestern University
    ## 1255               PHD 1969 Univ Catolique de Louvain
    ## 1256                      PHD 1986 Cornell University
    ## 1257                                            PHD  
    ## 1258                MS 2000 Univ of Wisconsin-Madison
    ## 1259                     PHD 2005 Stanford University
    ## 1260               PHD 1984 Univ of Wisconsin-Madison
    ## 1261               PHD 2009 Univ Of Minnesota-St Paul
    ## 1262                         MD 1990 Cairo University
    ## 1263           PHD 1989 Pennsylvania State University
    ## 1264                                         JD 2000 
    ## 1265                      PHD 1999 Harvard University
    ## 1266                         PHD 1989 Yale University
    ## 1267                     PHD 2011 Stanford University
    ## 1268                MD 1993 Univ of Wisconsin-Madison
    ## 1269                 PHD 1992 University Of Rochester
    ## 1270            MSN 2005 Univ of Wisconsin-Eau Claire
    ## 1271           PHD 2000 Univ of Michigan at Ann Arbor
    ## 1272               MSW 2015 Univ of Wisconsin-Madison
    ## 1273               PHD 2003 Univ of Wisconsin-Madison
    ## 1274                     PHD 2016 Columbia University
    ## 1275                      PHD 1980 Harvard University
    ## 1276                   DVM 1991 University of Georgia
    ## 1277             PHD 1987 Univ of California Berkeley
    ## 1278                MD 2010 Univ of Wisconsin-Madison
    ## 1279          MFA 1989 Sch Of The Art Inst Of Chicago
    ## 1280                PHD 2013 Univ Of NC At Greensboro
    ## 1281                    MSSW 2010 Columbia University
    ## 1282               PHD 1997 Univ Of NC At Chapel Hill
    ## 1283                MS 1983 Univ of Wisconsin-Madison
    ## 1284               PHD 2005 Univ of Wisconsin-Madison
    ## 1285               PHD 1999 Univ of Wisconsin-Madison
    ## 1286               PHD 1996 Univ of Wisconsin-Madison
    ## 1287              PHD 2006 Massachusetts Inst Of Tech
    ## 1288             PHD 2014 Univ of Colorado at Boulder
    ## 1289               PHD 1980 Colorado State University
    ## 1290                   PHD 2001 University of Reading
    ## 1291                MD 1988 Univ of Missouri-Columbia
    ## 1292            MD 1994 Univ of Michigan at Ann Arbor
    ## 1293                   PHD 2007 University of Wyoming
    ## 1294                   PHD 2009 A.T. Still University
    ## 1295                                            DPT  
    ## 1296                    DS  Univ of Wisconsin-Madison
    ## 1297               DVM 1993 Univ of Wisconsin-Madison
    ## 1298                    PHD 2018 Santa Monica College
    ## 1299                    PHD 1997 Princeton University
    ## 1300               PHD 1999 Univ of Wisconsin-Madison
    ## 1301               PHD 1998 Univ of Wisconsin-Madison
    ## 1302                MA 1993 Univ of Wisconsin-Madison
    ## 1303                MS 2014 Univ of Wisconsin-Madison
    ## 1304                MS 2017 Univ of Wisconsin-Madison
    ## 1305                 PHD 1984 Northwestern University
    ## 1306               PHD 1984 Univ of Wisconsin-Madison
    ## 1307           PHD 1997 Univ of Massachusetts Amherst
    ## 1308                                        DVM 2016 
    ## 1309           PHD 1999 Univ of Michigan at Ann Arbor
    ## 1310               DNP 2018 Univ of Wisconsin-Oshkosh
    ## 1311                   MFA  Univ of Wisconsin-Madison
    ## 1312                       PHD 2015 Auburn University
    ## 1313                      MFA 2013 Hollins University
    ## 1314            EDM 1987 Univ of Wisconsin-Whitewater
    ## 1315           PHD 2009 U of California-Santa Barbara
    ## 1316        PHARMD 1993 Univ of Minnesota-Twin Cities
    ## 1317             MSW 1999 Univ of California Berkeley
    ## 1318                BA 2000 Univ of Wisconsin-Madison
    ## 1319              PHD 2020 Georgia Inst of Technology
    ## 1320                JD 2012 Univ of Wisconsin-Madison
    ## 1321               DVM 2017 Univ of Wisconsin-Madison
    ## 1322                     MS  Johns Hopkins University
    ## 1323                     PHD 1989 Columbia University
    ## 1324               PHD 1987 Univ of Wisconsin-Madison
    ## 1325               PHD 1994 Univ of Wisconsin-Madison
    ## 1326             MSW 1999 Univ of MD Baltimore County
    ## 1327                      PHD 2000 University of Iowa
    ## 1328                   PHD 2016 Universitat Stuttgart
    ## 1329           BSE 2014 Univ of Michigan at Ann Arbor
    ## 1330                JD 1991 Univ of Wisconsin-Madison
    ## 1331                    MFA 1991 University of Oregon
    ## 1332             PHD 2000 Univ of Colorado at Boulder
    ## 1333             PHD 2005 Oregon Health Sciences Univ
    ## 1334                     MD 1990 University of Tehran
    ## 1335                      PHD 2013 University of Utah
    ## 1336               PHD 1987 Univ of Wisconsin-Madison
    ## 1337               MSW 2008 Univ of Wisconsin-Madison
    ## 1338                PHD 1990 Johns Hopkins University
    ## 1339               PHD 2017 Colorado State University
    ## 1340               PHD 2007 Univ of Wisconsin-Madison
    ## 1341             PHD 1993 Univ of California Berkeley
    ## 1342               PHD 1982 Univ of Wisconsin-Madison
    ## 1343               PHD 1989 Univ of Wisconsin-Madison
    ## 1344          PHD 2020 University of Hawaii-West Oahu
    ## 1345               PHD 2014 Univ Of NC At Chapel Hill
    ## 1346                      PHD 2003 University of Iowa
    ## 1347                     MSN 1996 St Louis University
    ## 1348               PHD 1998 Univ of Wisconsin-Madison
    ## 1349               DVM 1993 Michigan State University
    ## 1350           PHD 2003 Univ of Michigan at Ann Arbor
    ## 1351                 PHD 2019 Northeastern University
    ## 1352               PHD 2020 Univ of Wisconsin-Madison
    ## 1353                      MA 2004 New York University
    ## 1354                  PHD 2006 Katholieke Univ Leuven
    ## 1355               PHD 2009 Univ of Wisconsin-Madison
    ## 1356                   PHD 2008 University of Arizona
    ## 1357                    PHD 2004 University of Kansas
    ## 1358               PHD 2016 Univ of Wisconsin-Madison
    ## 1359          PHD 2010 Univ of IL at Urbana-Champaign
    ## 1360           PHD 1998 Univ of Maryland College Park
    ## 1361               PHD 2005 Univ of Wisconsin-Madison
    ## 1362                   MFA  Univ of Wisconsin-Madison
    ## 1363                   PHD 1999 University of Chicago
    ## 1364               PHD 2006 Univ of Wisconsin-Madison
    ## 1365                      PHD 2004 Harvard University
    ## 1366             PHD 2016 Univ of California Berkeley
    ## 1367               MS  Concordia University Wisconsin
    ## 1368               PHD 1995 Univ of Wisconsin-Madison
    ## 1369               MFA 2018 Univ of Wisconsin-Madison
    ## 1370                          MD 2007 Mayo Foundation
    ## 1371            MM 1992 New England Cnsrvtry Of Music
    ## 1372              PHD 2001 Univ Autonoma de Barcelona
    ## 1373             PHD 2014 Univ of Illinois at Chicago
    ## 1374               MSW 2015 Univ of Wisconsin-Madison
    ## 1375               PHD 1984 Univ of Wisconsin-Madison
    ## 1376               PHD 1979 Univ Of Minnesota-St Paul
    ## 1377                MS 1989 Univ of Wisconsin-Madison
    ## 1378              MPAS 1998 Univ of Nebraska at Omaha
    ## 1379               PHD 2003 University of Southampton
    ## 1380               EDM 2020 Univ of Wisconsin-Madison
    ## 1381                      PHD 2010 Indiana University
    ## 1382              MA 2004 Western Michigan University
    ## 1383                          PHD 2017 Boston College
    ## 1384             MFA 1997 Univ of Southern California
    ## 1385                      MSN 2006 Viterbo University
    ## 1386               EDM 1987 Univ of Wisconsin-Madison
    ## 1387                    PHD 1998 Princeton University
    ## 1388                   MFA 1997 Texas Tech University
    ## 1389                PHD 1985 University of Washington
    ## 1390                    PHD 1981 University of Oxford
    ## 1391                      PHD 2010 Indiana University
    ## 1392               PHD 2007 Univ of Wisconsin-Madison
    ## 1393            MD 2010 Univ of Minnesota-Twin Cities
    ## 1394                     PHD 2008 Columbia University
    ## 1395            PHD 2017 Univ of California San Diego
    ## 1396                MS 1982 Univ of Wisconsin-Madison
    ## 1397          PHD 2014 Univ of California Los Angeles
    ## 1398              MD 1983 Thomas Jefferson University
    ## 1399               PHD 2009 Univ of Wisconsin-Madison
    ## 1400                MS 2013 Univ of Wisconsin-Madison
    ## 1401                MD 2007 Univ of Wisconsin-Madison
    ## 1402                      DVM 2004 Cornell University
    ## 1403                MS 1991 Univ of Wisconsin-Madison
    ## 1404               MSW 2014 Univ of Wisconsin-Madison
    ## 1405            PHD 1997 Eberhard Karls Univ Tubingen
    ## 1406               PHD 2005 Univ of Wisconsin-Madison
    ## 1407                   PHD 1982 Washington University
    ## 1408                       MA 2014 University of Iowa
    ## 1409                                        PHD 2020 
    ## 1410                    PHD 2001 Princeton University
    ## 1411                                        DVM 2015 
    ## 1412               DVM 2014 Univ of Wisconsin-Madison
    ## 1413               PHD 2008 Univ of Wisconsin-Madison
    ## 1414                 MD 1995 University of Louisville
    ## 1415           PHD 2006 Univ of Michigan at Ann Arbor
    ## 1416           PHD 2015 Univ of Minnesota-Twin Cities
    ## 1417                                             MS  
    ## 1418                   PHD 1990 University of Bristol
    ## 1419           PHD 2010 International Univ in Germany
    ## 1420               PHD 2009 Univ of Wisconsin-Madison
    ## 1421               EDD 2012 Univ of Wisconsin-Madison
    ## 1422             PHD 2003 Univ of Illinois at Chicago
    ## 1423                      PHD 2007 Cornell University
    ## 1424          PHD 2003 Australian National University
    ## 1425              PHD 2006 Massachusetts Inst Of Tech
    ## 1426           PHD 1988 Univ of Minnesota-Twin Cities
    ## 1427               PHD 1998 Univ of Wisconsin-Madison
    ## 1428          PHD 2006 Queen's University at Kingston
    ## 1429                    PHD 2001 University of Oregon
    ## 1430               PHD 2020 Univ of Wisconsin-Madison
    ## 1431          PHD 2019 Univ of California Los Angeles
    ## 1432               PHD 1975 Univ of Wisconsin-Madison
    ## 1433             PHD 2012 Univ of Southern California
    ## 1434              PHD 1995 Virginia Commonwealth Univ
    ## 1435               PHD 2014 Univ of Wisconsin-Madison
    ## 1436                   PHD 1999 University of Chicago
    ## 1437                     PHD 1986 Columbia University
    ## 1438              PHD 2017 University of Pennsylvania
    ## 1439                   PHD 1994 University of Chicago
    ## 1440                     PHD 2013 Tsinghua University
    ## 1441                   PHD  North Carolina State Univ
    ## 1442             PHD 1982 Univ of Southern California
    ## 1443                 PHD 2017 Univ of New South Wales
    ## 1444             PHD 2017 City University Of New York
    ## 1445                 PHD 2011 George Mason University
    ## 1446                                        PHD 2018 
    ## 1447                        PHD 2003 Brown University
    ## 1448                      PHD 1998 Harvard University
    ## 1449                JD 1998 Univ of Wisconsin-Madison
    ## 1450                    DS  Univ Of Nevada, Las Vegas
    ## 1451            PHD 2004 Univ of California San Diego
    ## 1452               PHD 2005 Univ of Wisconsin-Madison
    ## 1453              MFA 2005 Virginia Commonwealth Univ
    ## 1454                     PHD 2010 Stanford University
    ## 1455           PHD 2000 U of California San Francisco
    ## 1456             PHD 2006 Univ of California Berkeley
    ## 1457                MD 1989 Univ of Wisconsin-Madison
    ## 1458                MA 2011 Univ of Wisconsin-Madison
    ## 1459                      PHD 1996 Harvard University
    ## 1460               PHD 1988 Univ of Wisconsin-Madison
    ## 1461          PHD 1999 University of Nebraska-Lincoln
    ## 1462               PHD 2009 Univ of Wisconsin-Madison
    ## 1463                   PHD 1984 University of Chicago
    ## 1464           PHARMD 1981 Univ of Tennessee, Memphis
    ## 1465                       MD 1988 Harvard University
    ## 1466                      PHD 2005 Harvard University
    ## 1467              PHD 2019 Univ of Texas at Arlington
    ## 1468                PHD 2012 Univ of California Davis
    ## 1469             PHD 1972 Univ of California Berkeley
    ## 1470                         PHD 1989 Yale University
    ## 1471               PHD 2010 Univ of California Irvine
    ## 1472                JD 1979 Univ of Wisconsin-Madison
    ## 1473                   PHD 2011 University of Chicago
    ## 1474                PHD 2012 Univ of California Davis
    ## 1475                     PHD 1997 University of Tokyo
    ## 1476                     PHD 1998 University of Tokyo
    ## 1477              MSSW 2005 Univ of Wisconsin-Madison
    ## 1478                MA 2014 Univ of Wisconsin-Madison
    ## 1479                      PHD 1988 Cornell University
    ## 1480                                        EDD 1997 
    ## 1481                PHD 2008 University of Copenhagen
    ## 1482               MLIS 2016 University of Washington
    ## 1483                MA 2005 Univ of Wisconsin-Madison
    ## 1484               MD 1989 University of Pennsylvania
    ## 1485              PHD 2012 St. Petersburg State Univ.
    ## 1486                    PHD 1988 Princeton University
    ## 1487          PHD 2004 Maharaja Sayajirao U of Baroda
    ## 1488                           EDM  DePaul University
    ## 1489                      EDM 2012 University of Iowa
    ## 1490               DVM 2010 Univ of Wisconsin-Madison
    ## 1491                MS 1996 Univ of Wisconsin-Madison
    ## 1492                      PHD 2000 University of Iowa
    ## 1493                         PHD 1977 Yale University
    ## 1494             PHD 2002 Univ of California Berkeley
    ## 1495             PHD 2016 Univ of Wisconsin-Milwaukee
    ## 1496             DNP 2017 Univ of Wisconsin-Milwaukee
    ## 1497                 MPH 2019 Grand Canyon University
    ## 1498                                        DVM 2016 
    ## 1499          PHD 1986 Univ of California Los Angeles
    ## 1500               PHD 2015 Univ of Wisconsin-Madison
    ## 1501              PHD 1978 Massachusetts Inst Of Tech
    ## 1502                   MD 1980 University Of Damascus
    ## 1503                   MD 1989 University of Virginia
    ## 1504               PHD 1984 Univ of Wisconsin-Madison
    ## 1505               PHD 2009 Univ of Wisconsin-Madison
    ## 1506                    PHD 1966 University of Oxford
    ## 1507             PHD 2010 Cardinal Stritch University
    ## 1508                         MA 2013 Lakeland College
    ## 1509       PHD 2007 Iowa State Univ of Sci &amp; Tech
    ## 1510           PHD 2018 University of Texas at Austin
    ## 1511               PHD 2008 Univ of Wisconsin-Madison
    ## 1512              PHD  Calif. State Univ. Los Angeles
    ## 1513                 PHD 1999 University of Ljubljana
    ## 1514               PHD 1994 Univ of Wisconsin-Madison
    ## 1515              PHD 1996 Carnegie-Mellon University
    ## 1516                      PHD 2001 Cornell University
    ## 1517                      PHD 1991 University of Iowa
    ## 1518                        PHD 2008 Brown University
    ## 1519                PHD 2016 University of Pittsburgh
    ## 1520                MA 2014 Univ of Wisconsin-Madison
    ## 1521                      PHD 2002 Cornell University
    ## 1522             PHD 2015 Univ of California Berkeley
    ## 1523               PHD 1978 Univ of Wisconsin-Madison
    ## 1524                       MD 1995 Harvard University
    ## 1525                    MS  Univ of Wisconsin-Madison
    ## 1526                      MPS 1996 Cornell University
    ## 1527               PHD 2000 Univ of Wisconsin-Madison
    ## 1528               PHD 2002 Univ of Wisconsin-Madison
    ## 1529           MS 2012 Embry Riddle Aeronautical Univ
    ## 1530            MS 1986 London Sch Econ&amp; Poli Sci
    ## 1531               PHD 2009 Univ of Wisconsin-Madison
    ## 1532               DS 1984 Massachusetts Inst Of Tech
    ## 1533               PHD 1992 Univ of Wisconsin-Madison
    ## 1534           PHD 2008 Pennsylvania State University
    ## 1535           PHD 1997 Univ of Michigan at Ann Arbor
    ## 1536               PHD 2008 Univ of Wisconsin-Madison
    ## 1537                         PHD 2019 Yale University
    ## 1538                   PHD  Univ of Wisconsin-Madison
    ## 1539                     PHD 1995 Columbia University
    ## 1540           MBA 1993 North Dakota State University
    ## 1541                MS 1992 Univ of Wisconsin-Madison
    ## 1542               PHD 2013 Univ of Wisconsin-Madison
    ## 1543               PHD 2008 Univ of Wisconsin-Madison
    ## 1544                       PHD 1993 Boston University
    ## 1545                      PHD 1990 University of Iowa
    ## 1546                PHD 1997 Brigham Young University
    ## 1547                         PHD 1993 Yale University
    ## 1548                   PHD 2010 University of Chicago
    ## 1549           PHD 2017 Univ of Michigan at Ann Arbor
    ## 1550            PHD 2014 Fielding Graduate University
    ## 1551                    MFA  Florida State University
    ## 1552               MSA 2002 Univ of Wisconsin-Madison
    ## 1553                   PHD 2018 University of Chicago
    ## 1554               PHD 2000 Univ of Wisconsin-Madison
    ## 1555                    DNP 2018 Marquette University
    ## 1556                   PHD 1993 University of Chicago
    ## 1557                        MFA 2005 Columbia College
    ## 1558                   MFA 2008 University of Arizona
    ## 1559             MS 1996 Univ of Wisconsin-Whitewater
    ## 1560                      PHD 2009 Heidelberg College
    ## 1561               PHD 1991 Univ of Wisconsin-Madison
    ## 1562              PHD 2001 Case Western Reserve Univ.
    ## 1563               PHD 2017 Univ of Wisconsin-Madison
    ## 1564                        PHD 2015 Brown University
    ## 1565           PHD 1982 Univ of Maryland College Park
    ## 1566               EDD 2015 Illinois State University
    ## 1567                                   BFA  Argentina
    ## 1568                        MA 1988 DePaul University
    ## 1569               PHD 1997 North Carolina State Univ
    ## 1570               PHD 1994 Seoul National University
    ## 1571                  MD 2007 Northwestern University
    ## 1572                       MAED  Marquette University
    ## 1573                 PHD 2007 Kansas State University
    ## 1574                MS 2006 Univ of Wisconsin-Madison
    ## 1575               PHD 1990 Univ Of Minnesota-St Paul
    ## 1576               PHD 1992 Univ Of Minnesota-St Paul
    ## 1577                MD 2012 Univ of Wisconsin-Madison
    ## 1578               PHD 1988 Univ of Missouri-Columbia
    ## 1579              PHD 1993 Massachusetts Inst Of Tech
    ## 1580                     PHD 2012 McMaster University
    ## 1581                  PHD 1997 University of Virginia
    ## 1582                                        MPH 1997 
    ## 1583                    DO 2013 Midwestern University
    ## 1584              MD 1976 Thomas Jefferson University
    ## 1585              MA 1979 Univ of Wisconsin-Milwaukee
    ## 1586               MFA 2000 Univ of Wisconsin-Madison
    ## 1587                      EDD 2015 Harvard University
    ## 1588                 PHD 2012 Northwestern University
    ## 1589                       MSA 1994 Purdue University
    ## 1590                   PHD 1987 University of Chicago
    ## 1591             PHD 1978 Univ of California Berkeley
    ## 1592          DNP 2015 Concordia University Wisconsin
    ## 1593              PHD 2015 University of Pennsylvania
    ## 1594               PHD 2010 Seoul National University
    ## 1595             MS 2012 Univ of Wisconsin-Whitewater
    ## 1596                    PHD 1995 Princeton University
    ## 1597                  EDD 2006 University of Delaware
    ## 1598          PHD 1987 Univ of California Los Angeles
    ## 1599                PHARMD  Univ of Wisconsin-Madison
    ## 1600               PHD 2005 Univ of Wisconsin-Madison
    ## 1601                        MAED  Salem State College
    ## 1602          PHD 1981 Univ of California Los Angeles
    ## 1603                  PHD 1994 Fachhochschule Munchen
    ## 1604                MM 1977 Univ of Wisconsin-Madison
    ## 1605               PHD 2015 Univ of Wisconsin-Madison
    ## 1606           PHD 1997 Pennsylvania State University
    ## 1607                                        PHD 1997 
    ## 1608                DM 2020 Univ of Wisconsin-Madison
    ## 1609                     JD 1983 Marquette University
    ## 1610       PHD 1986 Iowa State Univ of Sci &amp; Tech
    ## 1611                       JD 2004 University of Iowa
    ## 1612                    MD 2010 University of Chicago
    ## 1613               MBA 2010 Univ of Wisconsin-Madison
    ## 1614                      PHD 2013 Harvard University
    ## 1615                 PHD 2007 Northwestern University
    ## 1616               EDM 2013 Univ Of Missouri-St Louis
    ## 1617                     PHD 1983 Hokkaido University
    ## 1618           PHD 2014 U of California-Santa Barbara
    ## 1619        MS 1993 Iowa State Univ of Sci &amp; Tech
    ## 1620           MA 1980 Univ of IL at Urbana-Champaign
    ## 1621              MSSW 2002 Univ of Wisconsin-Madison
    ## 1622                         DNP 2016 Rush University
    ## 1623             PHD 1997 Univ of California Berkeley
    ## 1624                 PHD 2012 University Of Rochester
    ## 1625             PHD 2008 Univ of Colorado at Boulder
    ## 1626           PHD 2016 Univ of Minnesota-Twin Cities
    ## 1627                         PHD 2011 Mayo Foundation
    ## 1628               DVM 2016 Univ of Wisconsin-Madison
    ## 1629               PHD 2012 Univ Of NC At Chapel Hill
    ## 1630             PHD 2003 Univ of California Berkeley
    ## 1631                      PHD 2008 Cornell University
    ## 1632                       MA 2016 Middlebury College
    ## 1633                      PHD 1990 Cornell University
    ## 1634               PHD 2001 Rutgers State Univ-Newark
    ## 1635                     PHD 1993 Stanford University
    ## 1636                     JD 2009 Marquette University
    ## 1637                 PHD 1977 Northwestern University
    ## 1638          DVM 2002 Univ of IL at Urbana-Champaign
    ## 1639             MA 1989 Northern Illinois University
    ## 1640                   PHD  Univ of Wisconsin-Madison
    ## 1641               PHD 1999 Univ Of NC At Chapel Hill
    ## 1642                            BA 1977 Smith College
    ## 1643                JD 1991 Univ of Wisconsin-Madison
    ## 1644               PHD 2006 Univ of Wisconsin-Madison
    ## 1645                   MLA 1987 University of Arizona
    ## 1646                        PHD 2015 Universitat Bonn
    ## 1647                     PHD 2004 Stanford University
    ## 1648                    PHD 1998 Marquette University
    ## 1649                 PHD 1973 Northwestern University
    ## 1650                      PHD 2018 Harvard University
    ## 1651            DNP 2013 Univ of Wisconsin-Eau Claire
    ## 1652                          MD 1979 Yale University
    ## 1653               PHD 2009 Univ of Wisconsin-Madison
    ## 1654             PHD 1983 Univ of California Berkeley
    ## 1655           PHD 2006 University of Texas at Austin
    ## 1656                JD 1981 Univ of Wisconsin-Madison
    ## 1657                      MFA 1986 University of Iowa
    ## 1658                      PHD 1997 Harvard University
    ## 1659               PHD 2017 Claremont Mckenna College
    ## 1660                MS 2004 Univ of Wisconsin-Madison
    ## 1661                PHD 2001 Johns Hopkins University
    ## 1662          PHD 2020 Univ of IL at Urbana-Champaign
    ## 1663                                            PHD  
    ## 1664                   PHD 2012 Kent State University
    ## 1665          PHD 1994 Hebrew University of Jerusalem
    ## 1666                    PHD 1997 University of Mysore
    ## 1667            EDS 2016 Univ of Wisconsin-Whitewater
    ## 1668                MD 1997 Univ of Wisconsin-Madison
    ## 1669                MS 1984 Univ of Wisconsin-Madison
    ## 1670              MSSW 2007 Univ of Wisconsin-Madison
    ## 1671             MD 2005 Medical College Of Wisconsin
    ## 1672               DNP 2016 Univ of Wisconsin-Madison
    ## 1673          PHD 1987 Univ of IL at Urbana-Champaign
    ## 1674               PHD 2011 University of Connecticut
    ## 1675                        PHD 2011 Brown University
    ## 1676                     PHD 2007 Columbia University
    ## 1677          PHD 2016 Univ of California Los Angeles
    ## 1678          PHD 2001 Univ of IL at Urbana-Champaign
    ## 1679           PHD 1998 University of Texas at Austin
    ## 1680               PHD 1985 Univ of Wisconsin-Madison
    ## 1681           PHD 2011 Univ of Michigan at Ann Arbor
    ## 1682             PHD 2010 Univ of Illinois at Chicago
    ## 1683              PHD 2001 Georgia Inst of Technology
    ## 1684                PHD 2020 University of Washington
    ## 1685                PHD 2014 Florida State University
    ## 1686          PHD 2004 Univ of IL at Urbana-Champaign
    ## 1687               PHD 2013 Seoul National University
    ## 1688             PHD 1978 Univ of Colorado at Boulder
    ## 1689               PHD 1989 Univ of Wisconsin-Madison
    ## 1690               PHD 2003 Univ Of NC At Chapel Hill
    ## 1691               PHD 2003 Univ Of NC At Chapel Hill
    ## 1692                MD 2001 Univ of Wisconsin-Madison
    ## 1693               PHD 2010 Univ of Wisconsin-Madison
    ## 1694               PHD 1994 Univ of Wisconsin-Madison
    ## 1695                MA 2017 Univ of Wisconsin-Madison
    ## 1696                  PHD  Georgia Inst of Technology
    ## 1697                   PHD 1996 University of Arizona
    ## 1698            PHD 2012 Univ of California San Diego
    ## 1699               PHD 2017 Univ of Wisconsin-Madison
    ## 1700                         PHD 2012 Scripps College
    ## 1701               PHD 2017 Univ of Wisconsin-Madison
    ## 1702               PHD 2018 Univ of Wisconsin-Madison
    ## 1703           PHD 2016 University of Texas at Austin
    ## 1704           PHD 2007 Univ of Massachusetts Amherst
    ## 1705               PHD 1987 Univ of Wisconsin-Madison
    ## 1706           PHD 2016 Univ of Minnesota-Twin Cities
    ## 1707               PHD 2014 Univ of Wisconsin-Madison
    ## 1708               PHD 2008 Univ of Wisconsin-Madison
    ## 1709            MD 2010 Univ of Alabama at Birmingham
    ## 1710               PHD 2009 Univ of Wisconsin-Madison
    ## 1711                             PHD 1991 Netherlands
    ## 1712                        MD 1978 Boston University
    ## 1713                          MD 1985 Duke University
    ## 1714           PHD 2013 Univ of Minnesota-Twin Cities
    ## 1715                JD 2005 Univ of Wisconsin-Madison
    ## 1716          PHD 1990 Univ of IL at Urbana-Champaign
    ## 1717                      PHD 2007 Indiana University
    ## 1718               SJD 1997 Univ of Wisconsin-Madison
    ## 1719                PHD 2004 Arizona State University
    ## 1720                        BS 1992 Purdue University
    ## 1721                MD 2003 Univ of Wisconsin-Madison
    ## 1722                   PHD 1994 Washington University
    ## 1723                MD 2011 Univ of Wisconsin-Madison
    ## 1724                JD 2000 Univ of Wisconsin-Madison
    ## 1725                MS 2007 Univ of Wisconsin-Madison
    ## 1726               PHD 2012 Univ of Wisconsin-Madison
    ## 1727                 PHD 2004 Northwestern University
    ## 1728                MA 1988 Univ of Wisconsin-Madison
    ## 1729                      PHD 2006 University of Iowa
    ## 1730                       MM 2009 Indiana University
    ## 1731               PHD 2012 Univ of Wisconsin-Madison
    ## 1732                     MA 2001 Concordia University
    ## 1733                      PHD 2015 Harvard University
    ## 1734          MSN 2016 Chamberlain College of Nursing
    ## 1735               PHD 1990 Univ of Wisconsin-Madison
    ## 1736                          PHD 2016 Boston College
    ## 1737                   PHD 2012 Ball State University
    ## 1738           PHD 1988 Univ of Maryland College Park
    ## 1739                MS 2017 Univ of Wisconsin-Madison
    ## 1740                PHD  California Institute of Tech
    ## 1741                        MA 1983 Drexel University
    ## 1742               PHD 1991 Univ of Wisconsin-Madison
    ## 1743                                         JD 1981 
    ## 1744                MS 2008 Univ of Wisconsin-Madison
    ## 1745                         PHD 2007 Duke University
    ## 1746               PHD 2010 Univ of Wisconsin-Madison
    ## 1747              PHD 1977 Massachusetts Inst Of Tech
    ## 1748                PHD 2015 University of Washington
    ## 1749                   PHD  Univ of Wisconsin-Madison
    ## 1750                                        DVM 2015 
    ## 1751           PHD 1988 Univ of Minnesota-Twin Cities
    ## 1752               PHD 1984 Univ of Wisconsin-Madison
    ## 1753                MS 2002 Univ of Wisconsin-Madison
    ## 1754                JD 2011 Univ of Wisconsin-Madison
    ## 1755                MD 1988 Univ of Wisconsin-Madison
    ## 1756            EDM 1976 Northern Illinois University
    ## 1757               PHD 2020 Univ of Wisconsin-Madison
    ## 1758                MS 2001 Univ of Wisconsin-Madison
    ## 1759                 PHD 2005 Northwestern University
    ## 1760                     PHD 2013 Stanford University
    ## 1761              PHD 2018 Georgia Inst of Technology
    ## 1762                        AUD 2008 Salus University
    ## 1763             PHD 2011 Univ of California Berkeley
    ## 1764               MBA 2011 Univ of Wisconsin-Madison
    ## 1765                       MA 1999 Indiana University
    ## 1766               PHD 1992 Univ of Wisconsin-Madison
    ## 1767                         MSN 2016 Herzing College
    ## 1768              PHD 1996 Case Western Reserve Univ.
    ## 1769                     PHD 1993 Stanford University
    ## 1770             PHD 1991 Univ of Wisconsin-Milwaukee
    ## 1771               PHD 1997 Univ of Wisconsin-Madison
    ## 1772            BS 1979 Univ of Wisconsin-Platteville
    ## 1773           PHD 2017 Univ of Minnesota-Twin Cities
    ## 1774              MSSW 2005 Univ of Wisconsin-Madison
    ## 1775                MS 1994 Univ of Wisconsin-Madison
    ## 1776                MS 2013 Univ of Wisconsin-Madison
    ## 1777                 MS  Univ of Tennessee, Knoxville
    ## 1778              MS 1987 Univ of Wisconsin-La Crosse
    ## 1779                      MFA 1987 University of Iowa
    ## 1780                   MPA  Univ of Wisconsin-Madison
    ## 1781       DVM 1996 Tamil Nadu Vet &amp; Ani Sci Univ
    ## 1782               PHD 2019 Univ of Wisconsin-Madison
    ## 1783               PHD 1984 Univ of Wisconsin-Madison
    ## 1784                       BA 1979 Mount Mary College
    ## 1785               PHD 1994 Univ of Wisconsin-Madison
    ## 1786                   PHD 2010 University of Florida
    ## 1787               MS 2008 Georgia Inst of Technology
    ## 1788               PHD 1999 Univ of Wisconsin-Madison
    ## 1789             MD 2008 Highland Park Community Coll
    ## 1790          PHD 2020 Univ of California Los Angeles
    ## 1791                      PHD 1991 University of Utah
    ## 1792               PHD 2012 Michigan State University
    ## 1793                   PHD 1996 University of Chicago
    ## 1794               PHD 2005 Univ of Wisconsin-Madison
    ## 1795                MS 1996 Univ of Wisconsin-Madison
    ## 1796                MBA  Northern Illinois University
    ## 1797               PHD 2001 Univ Of Minnesota-St Paul
    ## 1798           BAS 2014 Univ of Wisconsin-Platteville
    ## 1799               PHD 2007 Univ of Wisconsin-Madison
    ## 1800               PHD 1968 Univ of Wisconsin-Madison
    ## 1801          PHD 2015 Univ of IL at Urbana-Champaign
    ## 1802                      PHD 1991 Cornell University
    ## 1803               PHD 2004 Univ of Wisconsin-Madison
    ## 1804               PHD 1994 Univ of Wisconsin-Madison
    ## 1805              MS 1987 Univ of Wisconsin-Milwaukee
    ## 1806             PHD 1975 Rensselaer Polytechnic Inst
    ## 1807               PHD 1985 Univ of Wisconsin-Madison
    ## 1808                      PHD 2008 Harvard University
    ## 1809               PHD 2006 Univ of Wisconsin-Madison
    ## 1810                    MD 2010 Vanderbilt University
    ## 1811               BBA 1972 Univ of Wisconsin-Madison
    ## 1812           PHD 1983 Univ of Michigan at Ann Arbor
    ## 1813                   PHD 1983 University of Chicago
    ## 1814              MD 2006 Univ of Illinois at Chicago
    ## 1815               EDD 2012 Univ of Wisconsin-Madison
    ## 1816                       BFA 2013 Alfred University
    ## 1817                   MFA  Rutgers State Univ-Newark
    ## 1818                PHD 2007 Univ of California Davis
    ## 1819              MSSW 1998 Univ of Wisconsin-Madison
    ## 1820                PHD 2007 Johns Hopkins University
    ## 1821                PHD 2003 University of Washington
    ## 1822                PHD 2005 University of Washington
    ## 1823            MS 2015 Minnesota State Univ, Mankato
    ## 1824               PHD 2014 Univ of Wisconsin-Madison
    ## 1825             PHD 1994 Univ of California Berkeley
    ## 1826               PHD 2017 Univ of Wisconsin-Madison
    ## 1827                          MS 2009 Bentley College
    ## 1828              MSSW 1996 Univ of Wisconsin-Madison
    ## 1829             PHD 1996 Univ of Southern California
    ## 1830                MD 2014 Univ of Wisconsin-Madison
    ## 1831       DVM 1987 Iowa State Univ of Sci &amp; Tech
    ## 1832               PHD 2012 Univ of Wisconsin-Madison
    ## 1833               PHD 2014 Univ of Wisconsin-Madison
    ## 1834              MSSW 1989 Univ of Wisconsin-Madison
    ## 1835               PHD 1989 Univ of Wisconsin-Madison
    ## 1836                      PHD 1983 University of Utah
    ## 1837             PHD 1992 Univ of California Berkeley
    ## 1838                          MM 2013 Yale University
    ## 1839                 PHD 1987 University Of Rochester
    ## 1840                MD 2011 Univ of Wisconsin-Madison
    ## 1841               PHD 1978 Univ of Wisconsin-Madison
    ## 1842             PHD 1984 Univ of California Berkeley
    ## 1843                 PHD 1995 University of Cambridge
    ## 1844                        MD 2005 Boston University
    ## 1845           MPH 2016 Univ of Massachusetts Amherst
    ## 1846               PHD 2001 Colorado State University
    ## 1847               PHD 1987 Univ of Wisconsin-Madison
    ## 1848              PHD 2016 Texas A &amp; M University
    ## 1849              MM 2006 Univ of Southern California
    ## 1850            PHD 1997 Univ of California San Diego
    ## 1851                         MA 2004 Edgewood College
    ## 1852               PHD 2009 Univ of Wisconsin-Madison
    ## 1853           PHD 2020 Univ of Michigan at Ann Arbor
    ## 1854           MFA 2006 Rhode Island School of Design
    ## 1855          PHD 1992 Univ of IL at Urbana-Champaign
    ## 1856                     MD 1996 University of Kansas
    ## 1857                 PHD  Univ of California Berkeley
    ## 1858               DVM 2017 Univ of Wisconsin-Madison
    ## 1859               AUD 2013 Univ of Wisconsin-Madison
    ## 1860              PHD 1991 University of Pennsylvania
    ## 1861             EDM 2014 Univ of Wisconsin-La Crosse
    ## 1862               PHD 1989 Univ of Wisconsin-Madison
    ## 1863                         AS 2011 Cabrillo College
    ## 1864                MS 1983 Univ of Wisconsin-Madison
    ## 1865               PHD 2018 Univ of Wisconsin-Madison
    ## 1866               PHD 2013 Univ of Wisconsin-Madison
    ## 1867                     PHD 2020 New York University
    ## 1868                   MA 2006 University of Oklahoma
    ## 1869                   PHD 2008 University of Florida
    ## 1870               PHD 2012 Univ of Wisconsin-Madison
    ## 1871                MA 2014 Univ of Wisconsin-Madison
    ## 1872                   PHD 1986 University of Chicago
    ## 1873               DVM 2003 Univ of Wisconsin-Madison
    ## 1874                 PHD 2002 Northwestern University
    ## 1875                        DVM 2016 Tufts University
    ## 1876               PHD 2009 Univ of Wisconsin-Madison
    ## 1877             PHD 1981 Univ of California Berkeley
    ## 1878                                        DVM 2011 
    ## 1879          PHD 1993 Univ of IL at Urbana-Champaign
    ## 1880                                        PHD 2018 
    ## 1881                     PHD 2011 Stanford University
    ## 1882           PHD 2009 Univ of Minnesota-Twin Cities
    ## 1883           PHD 2013 Univ of Minnesota-Twin Cities
    ## 1884                JD 1974 Univ of Wisconsin-Madison
    ## 1885                PHD 2005 Georgia State University
    ## 1886                PHD 2017 Johns Hopkins University
    ## 1887              PHD 2011 University of Pennsylvania
    ## 1888                       PHS  University of Florida
    ## 1889               PHD 1994 Michigan State University
    ## 1890             PHD 2006 Univ of California Berkeley
    ## 1891                JD 1999 Univ of Wisconsin-Madison
    ## 1892       PHD 2004 VA Polytechnic Inst &amp; State U
    ## 1893           MA 1989 Univ of California Los Angeles
    ## 1894          PHD 2013 Univ of California Los Angeles
    ## 1895           PHD 2000 Univ of Michigan at Ann Arbor
    ## 1896               PHD 2013 Univ of Wisconsin-Madison
    ## 1897          PHD 2000 Univ of IL at Urbana-Champaign
    ## 1898                         PHD 2008 Duke University
    ## 1899               PHD 2015 Univ of Wisconsin-Madison
    ## 1900               PHD 2013 Univ of Wisconsin-Madison
    ## 1901                      PHD 2017 Cornell University
    ## 1902             PHD 2004 Thomas Jefferson University
    ## 1903                   PHD 2009 Ohio State University
    ## 1904              PHD 1990 Massachusetts Inst Of Tech
    ## 1905              PHD 2017 Georgia Inst of Technology
    ## 1906                   PHD 2011 University of Chicago
    ## 1907              PHD 2014 Georgia Inst of Technology
    ## 1908            PHD 2013 Univ of California San Diego
    ## 1909                            MD 1996 Touro College
    ## 1910              MACC 2020 Univ of Wisconsin-Madison
    ## 1911           PHD 2013 Pennsylvania State University
    ## 1912                PHD 2000 Colorado School of Mines
    ## 1913                      PHD 2003 Indiana University
    ## 1914                      PHD 2007 Harvard University
    ## 1915             PHD 2014 National Univ. of Singapore
    ## 1916               PHARMD 2016 University of Oklahoma
    ## 1917               PHD 1988 Univ of Wisconsin-Madison
    ## 1918               PHD 2008 Univ of Wisconsin-Madison
    ## 1919               PHD 2017 Univ of Wisconsin-Madison
    ## 1920              PHD 1998 Georgia Inst of Technology
    ## 1921                                            PHD  
    ## 1922          PHD 1984 Univ of IL at Urbana-Champaign
    ## 1923                   PHD 2009 University of Chicago
    ## 1924                       PHD 2011 Purdue University
    ## 1925               PHD 2020 Univ of Wisconsin-Madison
    ## 1926               PHD 1985 Univ of Wisconsin-Madison
    ## 1927            PHARMD 2001 Univ of Wisconsin-Madison
    ## 1928               PHD 2017 Univ of Wisconsin-Madison
    ## 1929              PHD 1997 Carnegie-Mellon University
    ## 1930               PHD 2008 Univ of Wisconsin-Madison
    ## 1931                         MFA 2009 Yale University
    ## 1932           PHD 1991 Univ of Massachusetts Amherst
    ## 1933               PHD 2013 Univ of Wisconsin-Madison
    ## 1934           PHD 1993 SUNY Health Sci Cntr-Syracuse
    ## 1935              MD 1997 Thomas Jefferson University
    ## 1936              PHD 2013 Georgia Inst of Technology
    ## 1937                   PHD 2006 Ohio State University
    ## 1938              PHD 2019 University of Pennsylvania
    ## 1939                      PHD 2001 Harvard University
    ## 1940               PHD 1990 University of Connecticut
    ## 1941               PHD 2010 Univ of Wisconsin-Madison
    ## 1942               PHD 2012 Univ of Wisconsin-Madison
    ## 1943              PHD 2010 Univ degli Studi di Milano
    ## 1944            PHD 2016 Univ of California San Diego
    ## 1945              MD 2000 Univ of Illinois at Chicago
    ## 1946               PHD 1988 Univ Of NC At Chapel Hill
    ## 1947               DVM 2015 Colorado State University
    ## 1948               PHD 2005 Colorado State University
    ## 1949                    JD 2003 Washington University
    ## 1950             PHD 2014 Univ of California Berkeley
    ## 1951             PHD 1982 Univ of California Berkeley
    ## 1952                     PHD 2006 Stanford University
    ## 1953           PHD 1993 Univ Of Maryland At Baltimore
    ## 1954                PHD 2020 Florida State University
    ## 1955                MD 2009 Univ of Wisconsin-Madison
    ## 1956                       MBA  Pepperdine University
    ## 1957        PHD 2017 Hong Kong Univ of Sci &amp; Tech
    ## 1958             MD 1990 Medical College Of Wisconsin
    ## 1959               PHD 2013 Univ of Wisconsin-Madison
    ## 1960                      PHD 2011 Indiana University
    ## 1961             PHD 2012 Univ of Southern California
    ## 1962                 PHD 2006 Universidad Veracruzana
    ## 1963               PHD 2017 Univ of Wisconsin-Madison
    ## 1964               PHD 1992 Univ of Wisconsin-Madison
    ## 1965             MSN 2012 Maryville Univ Of St. Louis
    ## 1966             DNP 2012 Univ of Wisconsin-Milwaukee
    ## 1967                                       MSED 2014 
    ## 1968                PHD 2001 Arizona State University
    ## 1969                      PHD 1988 Cornell University
    ## 1970             PHD 2015 Univ of California Berkeley
    ## 1971                    PHD 2018 University of Kansas
    ## 1972               PHD 2012 Univ of Wisconsin-Madison
    ## 1973           MFA 2009 Rhode Island School of Design
    ## 1974            PHD 2005 U of California Ext-Berkeley
    ## 1975                         PHD 2017 Yale University
    ## 1976                MD 2003 Univ of Wisconsin-Madison
    ## 1977                          MD 2013 Yale University
    ## 1978               PHD 2016 Univ of Wisconsin-Madison
    ## 1979                          PHD 1992 Ireland (Eire)
    ## 1980           MD 1985 Univ of Dublin-Trinity College
    ## 1981            PHD 2013 Mississippi State University
    ## 1982               PHD 2011 Univ of Wisconsin-Madison
    ## 1983               PHD 2018 Univ of Wisconsin-Madison
    ## 1984                                            PHD  
    ## 1985              PHD 2007 Georgia Inst of Technology
    ## 1986               MBA 2001 Univ of Wisconsin-Madison
    ## 1987               PHD 2007 Univ of California Irvine
    ## 1988               DVM 2007 Univ of Wisconsin-Madison
    ## 1989              PHD 2007 Carnegie-Mellon University
    ## 1990                         PHD 2015 SUNY at Buffalo
    ## 1991                 PHD 1987 Oregon State University
    ## 1992            MD 1993 Univ of Kansas Medical Center
    ## 1993               PHD 2014 Michigan State University
    ## 1994            PHD 1999 California Institute of Tech
    ## 1995               PHD 1984 Univ of Wisconsin-Madison
    ## 1996              PHD 2019 Massachusetts Inst Of Tech
    ## 1997           PHD 2001 Univ of Michigan at Ann Arbor
    ## 1998                   MFA 2005 University of Montana
    ## 1999             PHD 1987 Univ of California Berkeley
    ## 2000          PHD 1986 Univ of California Los Angeles
    ## 2001               MFA 2017 Univ of Wisconsin-Madison
    ## 2002               PHD 1983 Michigan State University
    ## 2003             PHD 2018 Univ of Illinois at Chicago
    ## 2004          PHD 2016 Technische Universitat Munchen
    ## 2005            PHD 2002 Univ of Missouri-Kansas City
    ## 2006                    PHD 2011 Princeton University
    ## 2007                BS 2014 Univ of Wisconsin-Madison
    ## 2008                JD 2014 Univ of Wisconsin-Madison
    ## 2009               PHD 2017 Univ of Wisconsin-Madison
    ## 2010            PHD 1991 Univ of California San Diego
    ## 2011               PHD 2006 Michigan State University
    ## 2012           PHARMD 2017 Univ of Colorado at Denver
    ## 2013                 MBBS 1987 Guntur Medical College
    ## 2014                         PHD 2016 Yale University
    ## 2015                 PHD 2002 Northwestern University
    ## 2016                MS 1992 Univ of Wisconsin-Madison
    ## 2017           PHD 2011 Univ of Michigan at Ann Arbor
    ## 2018                 PHD 2012 Southwestern University
    ## 2019                JD 1995 Univ of Wisconsin-Madison
    ## 2020                   PHD 2015 Washington University
    ## 2021                   PHD 2015 Washington University
    ## 2022                MD 1967 Univ of Wisconsin-Madison
    ## 2023                         MA 2012 Edgewood College
    ## 2024                PHD 2005 Johns Hopkins University
    ## 2025              MA 1991 Univ of California Berkeley
    ## 2026                   PHD  Univ of Wisconsin-Madison
    ## 2027             PHD 2015 Univ of Wisconsin-Milwaukee
    ## 2028                       MS 2016 Harvard University
    ## 2029               PHD 2009 Univ of Wisconsin-Madison
    ## 2030                    PHD 2005 Princeton University
    ## 2031                     PHD 2001 Stanford University
    ## 2032                         MS 1994 McDaniel College
    ## 2033                MS 1998 Univ of Wisconsin-Madison
    ## 2034                     DVM 2006 Universitat Leipzig
    ## 2035               PHD 2016 Univ Of NC At Chapel Hill
    ## 2036               PHD 2020 Univ of Wisconsin-Madison
    ## 2037              PHD 2004 Carnegie-Mellon University
    ## 2038                      PHD 1999 Indiana University
    ## 2039                 PHD 2011 Oregon State University
    ## 2040               PHD 1992 Oklahoma State University
    ## 2041               PHD 1994 Univ of Wisconsin-Madison
    ## 2042               PHD 1987 Univ of Wisconsin-Madison
    ## 2043            PHARMD 2009 Univ of Wisconsin-Madison
    ## 2044           PHD 1991 Univ of Minnesota-Twin Cities
    ## 2045             PHD 2006 Univ of California Berkeley
    ## 2046               PHD 2003 Univ of Wisconsin-Madison
    ## 2047                         PHD 1990 Mayo Foundation
    ## 2048                     PHD 1998 Stanford University
    ## 2049                PHD 1990 Arizona State University
    ## 2050               PHD 2011 Colorado State University
    ## 2051             DVM 2005 Universidad de Buenos Aires
    ## 2052               PHD 1983 Univ of Wisconsin-Madison
    ## 2053              MS 2004 Univ of Wisconsin-La Crosse
    ## 2054                MS 2020 Univ of Wisconsin-Madison
    ## 2055                         PHD 1998 Yale University
    ## 2056            PHD 2009 Univ of California Riverside
    ## 2057                    PHD 2010 Princeton University
    ## 2058              PHD 2015 Massachusetts Inst Of Tech
    ## 2059      PHD 1993 Clg of William &amp; Mary-Virginia
    ## 2060               PHD 2006 Univ of Wisconsin-Madison
    ## 2061                MS 2004 Univ of Wisconsin-Madison
    ## 2062                MA 2009 Univ of Wisconsin-Madison
    ## 2063               EDD 2009 Univ of Wisconsin-Madison
    ## 2064                PHD 1992 University of Washington
    ## 2065                MS 2007 Univ of Wisconsin-Madison
    ## 2066                      PHD 1989 Harvard University
    ## 2067                      PHD 1974 Harvard University
    ## 2068               PHD 2016 Univ of Wisconsin-Madison
    ## 2069                                        PHD 2016 
    ## 2070               MBA 2005 Univ of Wisconsin-Madison
    ## 2071               PHD 1995 Univ Of Minnesota-St Paul
    ## 2072                 PHD 2001 Simon Fraser University
    ## 2073               PHD 1995 Univ of Wisconsin-Madison
    ## 2074                   PHD 2008 University of Arizona
    ## 2075           PHD 2006 Univ of Minnesota-Twin Cities
    ## 2076            PHD 1985 Fac Des Sci Agro DE Gembloux
    ## 2077                         PHD 2001 Rice University
    ## 2078               PHD 2013 Univ of Wisconsin-Madison
    ## 2079             PHD 1983 Univ of California Berkeley
    ## 2080          PHD 1984 University of British Columbia
    ## 2081                   PHD 2010 Vanderbilt University
    ## 2082               MSW 2014 Univ of Wisconsin-Madison
    ## 2083             EDM 2018 Univ of Wisconsin-La Crosse
    ## 2084               PHD 2014 Univ of Wisconsin-Madison
    ## 2085           MS 2015 Univ of California Los Angeles
    ## 2086               MFA 2017 Univ of Wisconsin-Madison
    ## 2087           PHD 1994 Univ of Michigan at Ann Arbor
    ## 2088          PHD 1987 Univ of IL at Urbana-Champaign
    ## 2089              PHD 2005 University of Pennsylvania
    ## 2090                         PHD 1988 Yale University
    ## 2091              JD 1991 Chicago-Kent College Of Law
    ## 2092                   PHD 1997 University of Arizona
    ## 2093           PHD 1979 U of California-Santa Barbara
    ## 2094               PHD 1994 Univ of Wisconsin-Madison
    ## 2095               PHD 1971 Univ of Wisconsin-Madison
    ## 2096               PHD 1991 Univ of Wisconsin-Madison
    ## 2097              MA 1998 Univ of Wisconsin-Milwaukee
    ## 2098           PHD 1989 Univ of Minnesota-Twin Cities
    ## 2099               MFA 1989 Univ of Wisconsin-Madison
    ## 2100             PHD 2009 Univ of California Berkeley
    ## 2101               MFA 2010 Univ of Wisconsin-Madison
    ## 2102                       JD 2003 University of Iowa
    ## 2103                 MA 2018 Johns Hopkins University
    ## 2104             MS 1991 Southern IL Univ.-Carbondale
    ## 2105             PHD 2011 Univ of Southern California
    ## 2106                      PHD 2009 Harvard University
    ## 2107                       PHD 1993 Purdue University
    ## 2108               PHD 2016 Univ of Wisconsin-Madison
    ## 2109                         PHD 1977 Yale University
    ## 2110                 PHD 2005 Northwestern University
    ## 2111               MD 2010 Case Western Reserve Univ.
    ## 2112              MD 2001 Thomas Jefferson University
    ## 2113                      PHD 2004 University of Utah
    ## 2114                     MM  University of Washington
    ## 2115                 PHD 1988 Northwestern University
    ## 2116              JD 2000 Univ of California Berkeley
    ## 2117             PHD 2002 Univ of California Berkeley
    ## 2118                     PHD 1988 Columbia University
    ## 2119                JD 2020 Univ of Wisconsin-Madison
    ## 2120                   PHD 2018 University of Chicago
    ## 2121                          MBA  University of Iowa
    ## 2122                          PHD  University of Iowa
    ## 2123                                        PHD 2011 
    ## 2124                    PHD 2017 Princeton University
    ## 2125           PHD 2000 University of Texas at Austin
    ## 2126               DNP 2012 Univ of Wisconsin-Madison
    ## 2127                EDD 2010 Univ of Minnesota-Duluth
    ## 2128          PHD 2005 Univ of California Los Angeles
    ## 2129                 PHD 1978 University of Cambridge
    ## 2130             PHD 2011 Univ of California Berkeley
    ## 2131                PHD 2008 Arizona State University
    ## 2132                   MD 1983 Wayne State University
    ## 2133                    PHD 2000 University of London
    ## 2134                BA 2011 Univ of Wisconsin-Madison
    ## 2135             PHD 2002 Univ of California Berkeley
    ## 2136          PHD 1985 Univ of California Los Angeles
    ## 2137                         PHD  New York University
    ## 2138               PHD 2007 Univ of Wisconsin-Madison
    ## 2139             DNP 2018 Univ of Illinois at Chicago
    ## 2140                JD 1993 Univ of Wisconsin-Madison
    ## 2141                   PHD 1992 University of Chicago
    ## 2142                 PHD 2017 Northwestern University
    ## 2143               PHD 1994 Univ of Wisconsin-Madison
    ## 2144                MD 2002 Univ of Wisconsin-Madison
    ## 2145            PHD 1996 California Institute of Tech
    ## 2146            PHD 1990 Univ of California San Diego
    ## 2147               PHD 2015 Univ of Wisconsin-Madison
    ## 2148              MD 1999 Univ of Illinois at Chicago
    ## 2149                      PHD 2004 Harvard University
    ## 2150               MSW 2007 Univ of Wisconsin-Madison
    ## 2151               PHD 1977 Univ of Wisconsin-Madison
    ## 2152            MS 2011 Minnesota State Univ, Mankato
    ## 2153                    PHD 1987 University of London
    ## 2154               PHD 1999 Univ of Wisconsin-Madison
    ## 2155                     PHD 2002 Columbia University
    ## 2156                                         MS 2011 
    ## 2157                   PHD 1994 University of Toronto
    ## 2158                PHD 2014 University of Washington
    ## 2159                       PHD 2006 Boston University
    ## 2160                                            PHD  
    ## 2161           PHD 2008 Univ of Michigan at Ann Arbor
    ## 2162                     PHD 1975 Stanford University
    ## 2163                 PHD 2011 University of San Diego
    ## 2164               MSW 2007 Univ of Wisconsin-Madison
    ## 2165                    PHD  University of Pittsburgh
    ## 2166               PHD 1990 Univ of Wisconsin-Madison
    ## 2167               PHD 1988 Univ of Wisconsin-Madison
    ## 2168                  PSYD 2018 University of Arizona
    ## 2169               PHD 2007 Univ of Wisconsin-Madison
    ## 2170            PHD 1996 Medical College Of Wisconsin
    ## 2171                    MS 1987 University Of Houston
    ## 2172                   PHD 2005 University of Arizona
    ## 2173                 PHD 2003 Northwestern University
    ## 2174             JD 2000 Hastings Clg of Law, U of CA
    ## 2175         MHEA 2002 Univ of IL at Urbana-Champaign
    ## 2176                   MPP 1995 University of Chicago
    ## 2177                     PHD 1998 Stanford University
    ## 2178          PHD 2012 Univ Studi di Roma-La Sapienza
    ## 2179                MS 2017 Univ of Wisconsin-Madison
    ## 2180               PHD 1976 Univ of Wisconsin-Madison
    ## 2181             PHD 2013 Univ of California Berkeley
    ## 2182               PHD 1996 Univ of Wisconsin-Madison
    ## 2183             PHD 1988 Universite Paris X Nanterre
    ## 2184                MS 1999 Univ of Wisconsin-Madison
    ## 2185            PHD 1981 California Institute of Tech
    ## 2186               PHD 2017 Univ of Wisconsin-Madison
    ## 2187                PHD 2007 Arizona State University
    ## 2188               PHD 1976 Univ of Wisconsin-Madison
    ## 2189             PHD 1984 Univ of California Berkeley
    ## 2190               MFA 1995 Univ of Wisconsin-Madison
    ## 2191           MSW 1996 Univ of Michigan at Ann Arbor
    ## 2192              PHD 2005 Massachusetts Inst Of Tech
    ## 2193              PHD 1995 Carnegie-Mellon University
    ## 2194               MS 1984 Carnegie-Mellon University
    ## 2195                      PHD 2002 Cornell University
    ## 2196                BS 1986 Univ of Wisconsin-Madison
    ## 2197               DVM 1983 Michigan State University
    ## 2198                      PHD 2005 University of Utah
    ## 2199              MFA 2013 Carnegie-Mellon University
    ## 2200                      PHD 2017 Cornell University
    ## 2201             PHD 2001 Univ of California Berkeley
    ## 2202             PHD 2020 Univ of Southern California
    ## 2203            MD 2012 Univ of Massachusetts Med Sch
    ## 2204                 PHD  Univ of California Berkeley
    ## 2205                 PHD 2017 Northwestern University
    ## 2206               PHD 2017 Univ of Wisconsin-Madison
    ## 2207                    JD 1987 Vanderbilt University
    ## 2208               PHD 2016 Univ of Wisconsin-Madison
    ## 2209                JD 2003 Univ of Wisconsin-Madison
    ## 2210            PHD 2002 Univ of Missouri-Kansas City
    ## 2211                JD 2010 Univ of Wisconsin-Madison
    ## 2212           MFA 2008 Univ of Maryland College Park
    ## 2213       PHD 1999 Iowa State Univ of Sci &amp; Tech
    ## 2214                         MLS 2002 SUNY at Buffalo
    ## 2215               PHD 1988 Univ of Wisconsin-Madison
    ## 2216             PHD 1990 Univ of California Berkeley
    ## 2217                     JD 1989 Marquette University
    ## 2218               PHD 1985 Univ of Wisconsin-Madison
    ## 2219               PHD 2015 Univ of Wisconsin-Madison
    ## 2220           PHD 1992 Al Ludwig U-Freiburg Breisgau
    ## 2221             PHD 2012 Univ of California Berkeley
    ## 2222                   MD 1992 University of Khartoum
    ## 2223                       PHD 2011 Shiraz University
    ## 2224                      PHD 2012 University of Iowa
    ## 2225                      PHD 2014 Harvard University
    ## 2226               PHD 2014 Univ of Wisconsin-Madison
    ## 2227                         PHD 2016 Yale University
    ## 2228           PHD 1985 Univ of Minnesota-Twin Cities
    ## 2229              MS 2004 Univ of Wisconsin-Milwaukee
    ## 2230                     JD 1988 University of Oregon
    ## 2231               MFA 2018 Univ of Wisconsin-Madison
    ## 2232              MACC 2020 Univ of Wisconsin-Madison
    ## 2233             PHD 2013 Univ of Wisconsin-Milwaukee
    ## 2234               MPA 2002 Univ of Wisconsin-Madison
    ## 2235                     PHD 2010 University Of Miami
    ## 2236               MSW 2012 Univ of Wisconsin-Madison
    ## 2237                  PHD 2006 University of Kentucky
    ## 2238                 PHD 1993 Northwestern University
    ## 2239                     PHD 1998 Columbia University
    ## 2240                      DVM 2006 Cornell University
    ## 2241               PHD 2004 Univ of Wisconsin-Madison
    ## 2242             MD 2000 George Washington University
    ## 2243               MD 2010 University of Pennsylvania
    ## 2244             PHD 1998 Univ of California Berkeley
    ## 2245              PHD 1994 Massachusetts Inst Of Tech
    ## 2246               PHD 1996 Univ of Wisconsin-Madison
    ## 2247                       JD 1979 Hofstra University
    ## 2248                       PHD 2010 McGill University
    ## 2249                JD 2006 Univ of Wisconsin-Madison
    ## 2250                      PHD 2009 Harvard University
    ## 2251                 PHD  Univ of Illinois at Chicago
    ## 2252                 PHD 2003 Northwestern University
    ## 2253           PHD 1983 Univ of Michigan at Ann Arbor
    ## 2254          PHD 2003 Univ of California Los Angeles
    ## 2255                       MD 1968 Harvard University
    ## 2256                         PHD 1999 Yale University
    ## 2257               PHD 1995 Univ of Wisconsin-Madison
    ## 2258                       PHD 2013 Purdue University
    ## 2259                PHD 2019 University of Pittsburgh
    ## 2260                                        PHD 2009 
    ## 2261               PHD 2008 Univ of Wisconsin-Madison
    ## 2262                PHD 2019 University of Washington
    ## 2263               PHD 2017 Univ of Wisconsin-Madison
    ## 2264                   PHD 1990 University of Bristol
    ## 2265              PHD 2014 University of Pennsylvania
    ## 2266                      PHD 2015 Cornell University
    ## 2267                    PHD 2018 Princeton University
    ## 2268                  PHD 1985 University of Virginia
    ## 2269         MMED 2013 Univ of IL at Urbana-Champaign
    ## 2270               PHD 2014 Univ of Wisconsin-Madison
    ## 2271                      PHD 1994 University of Iowa
    ## 2272            PHD 2012 Univ Paris Sorbonne Paris IV
    ## 2273           PHD 1989 Univ of Minnesota-Twin Cities
    ## 2274               DVM 2007 Univ of Missouri-Columbia
    ## 2275                          PHD 2016 Ireland (Eire)
    ## 2276                        MTECH 2002 Lesley College
    ## 2277                MS 1992 Univ of Wisconsin-Madison
    ## 2278                ME 2010 Univ of Wisconsin-Madison
    ## 2279              PHD 1989 Massachusetts Inst Of Tech
    ## 2280           PHD 2002 Univ of Michigan at Ann Arbor
    ## 2281               MSW 2008 Univ of Wisconsin-Madison
    ## 2282           EDD 2006 Univ of Minnesota-Twin Cities
    ## 2283                   PHD 2007 University of Chicago
    ## 2284                MA 1981 Univ of Wisconsin-Madison
    ## 2285              PHD 2009 Carnegie-Mellon University
    ## 2286              PHD 2007 Pittsburg State University
    ## 2287                  PHD 2003 Heriot-Watt University
    ## 2288                   PHD 2016 University of Chicago
    ## 2289                               MA 2002 Kazan Univ
    ## 2290                MD 2011 Univ of Wisconsin-Madison
    ## 2291                MS 2002 Univ of Wisconsin-Madison
    ## 2292                MD 2009 Univ of Wisconsin-Madison
    ## 2293                     PHD 1986 Columbia University
    ## 2294                                            PHD  
    ## 2295                  MD 1988 University Of Rochester
    ## 2296                      PHD 2011 University of Iowa
    ## 2297               PHD 2018 Univ of Wisconsin-Madison
    ## 2298               PHD 2020 Univ of Wisconsin-Madison
    ## 2299                MA 2005 Universidade de Sao Paulo
    ## 2300             PHD 1991 Univ of Colorado at Boulder
    ## 2301                      PHD 1985 Harvard University
    ## 2302                   PHD 1997 University of Florida
    ## 2303           MD 2005 Univ of IL at Urbana-Champaign
    ## 2304            MA 1998 State U of New York at Albany
    ## 2305          PHD 1992 Kazakh State U of World Langs.
    ## 2306               MSW 2013 Univ of Wisconsin-Madison
    ## 2307                      PHD 1998 University of Iowa
    ## 2308              PHD 1997 Massachusetts Inst Of Tech
    ## 2309                   PHD 1981 University of Chicago
    ## 2310           PHD 2008 University of Texas at Austin
    ## 2311                        PHD 1998 Brown University
    ## 2312               PHD 2017 Univ of Wisconsin-Madison
    ## 2313                     DMA 2007 SUNY At Stony Brook
    ## 2314               PHD 2013 Univ of Wisconsin-Madison
    ## 2315                         DPT 2007 Duke University
    ## 2316                     BA 1989 Marquette University
    ## 2317                MS 1995 Univ of Wisconsin-Madison
    ## 2318                         PHD 2013 Yale University
    ## 2319                MS 1976 Univ of Wisconsin-Madison
    ## 2320                      PHD 2011 Cornell University
    ## 2321               PHD 2010 Univ of Wisconsin-Madison
    ## 2322                         MS 2017 Edgewood College
    ## 2323             PHD 2007 Univ of California Berkeley
    ## 2324                   PHD 1994 University of Chicago
    ## 2325                MS 2012 Univ of Wisconsin-Madison
    ## 2326                   PHD  Univ of Wisconsin-Madison
    ## 2327          MSN 2014 Concordia University Wisconsin
    ## 2328               PHD 2004 University of New Orleans
    ## 2329               PHD 2008 Univ of Wisconsin-Madison
    ## 2330                    PHD 1998 Princeton University
    ## 2331          PHD 1972 Univ of IL at Urbana-Champaign
    ## 2332               DVM 2003 Univ of Wisconsin-Madison
    ## 2333                     PHD 2016 American University
    ## 2334             PHD 2010 Univ of Colorado at Boulder
    ## 2335               DNP 2012 Univ of Wisconsin-Madison
    ## 2336                PHD 1991 University of Washington
    ## 2337                PHD 1986 Univ of California Davis
    ## 2338                   PHD 1998 Univ de Strasbourg II
    ## 2339             MSW 1999 Washington State University
    ## 2340               PHD 2005 University of Connecticut
    ## 2341           MFA 2012 Univ of Michigan at Ann Arbor
    ## 2342                      PHD 2016 Indiana University
    ## 2343                DVM 2008 Univ of California Davis
    ## 2344               EDD 2015 Univ Of NC At Chapel Hill
    ## 2345                   PHD 1987 University of Calgary
    ## 2346                    MS  Univ of Wisconsin-Madison
    ## 2347           PHD 1987 Univ of Michigan at Ann Arbor
    ## 2348               PHD 1982 Univ of Wisconsin-Madison
    ## 2349                      SJD 2015 Harvard University
    ## 2350               PHD 2010 Univ of Wisconsin-Madison
    ## 2351               PHD 2009 Univ of Wisconsin-Madison
    ## 2352                MA 2006 Univ of Wisconsin-Madison
    ## 2353                   PHD 1999 Vanderbilt University
    ## 2354                      PHD 2010 Harvard University
    ## 2355          PHD 2007 Univ of California Los Angeles
    ## 2356          PHD 1995 Univ of IL at Urbana-Champaign
    ## 2357               DNP 2015 Univ of Wisconsin-Madison
    ## 2358                      THD 1994 Harvard University
    ## 2359                MA 2000 Univ of Wisconsin-Madison
    ## 2360               DNP 2020 Univ of Wisconsin-Madison
    ## 2361            PHD 2013 California Institute of Tech
    ## 2362               PHD 1995 Univ of Wisconsin-Madison
    ## 2363              PHD 1999 Texas A &amp; M University
    ## 2364                PHD 1985 Johns Hopkins University
    ## 2365                MA 2006 Univ of Wisconsin-Madison
    ## 2366              PHD 1986 University of Pennsylvania
    ## 2367                        BBA 1979 Drake University
    ## 2368                 MS 1982 University of Cincinnati
    ## 2369               PHD 2001 Univ of Wisconsin-Madison
    ## 2370                PHD 1985 University of Washington
    ## 2371                MS 2005 Univ of Wisconsin-Madison
    ## 2372               PHD 2017 Univ of Wisconsin-Madison
    ## 2373                      PHD 2019 Capella University
    ## 2374               PHD 2010 Univ of Wisconsin-Madison
    ## 2375                    MD 2006 Ohio State University
    ## 2376                    MD 2000 Georgetown University
    ## 2377               PHD 2001 Univ of Wisconsin-Madison
    ## 2378               PHD 2004 Univ of Wisconsin-Madison
    ## 2379                BA 2016 Univ of Wisconsin-Madison
    ## 2380               PHD 2019 Univ of Wisconsin-Madison
    ## 2381                      MD 1987 New York University
    ## 2382           DMA 2019 Univ of Michigan at Ann Arbor
    ## 2383                   DVM 1981 Ohio State University
    ## 2384                  PHD  Carnegie-Mellon University
    ## 2385           PHD 1982 University of Texas at Austin
    ## 2386                      PHD 2018 Harvard University
    ## 2387               PHD 2010 Univ Of NC At Chapel Hill
    ## 2388                JD 1986 Univ of Wisconsin-Madison
    ## 2389                      SJD 2001 Harvard University
    ## 2390           PHD 2009 Univ of Alabama at Birmingham
    ## 2391                   JD 1996 University Of Richmond
    ## 2392                   PHD 1996 University of Bristol
    ## 2393                          JD 2014 Yale University
    ## 2394                MS 1978 Univ of Wisconsin-Madison
    ## 2395            MSSW 1991 Univ of Wisconsin-Milwaukee
    ## 2396               PHD 1977 Univ Of NC At Chapel Hill
    ## 2397               PHD 1990 Univ Of NC At Chapel Hill
    ## 2398                    PHD 2014 University of Guelph
    ## 2399                      PHD 1992 Cornell University
    ## 2400          PHD 2010 Univ of IL at Urbana-Champaign
    ## 2401                MD 1982 Univ of Wisconsin-Madison
    ## 2402    PHD 2009 Louisiana State U &amp; A&amp;M Colg
    ## 2403               PHD 2005 Michigan State University
    ## 2404                BS 2005 Univ Of Minnesota-St Paul
    ## 2405                      MBA 1992 Harvard University
    ## 2406                         PHD 1984 Rice University
    ## 2407               PHD 2007 Univ of Wisconsin-Madison
    ## 2408                MS 2004 Univ of Wisconsin-Madison
    ## 2409                         PHD  Stanford University
    ## 2410                MD 2002 Univ of Wisconsin-Madison
    ## 2411           MS 1997 University of Nebraska-Lincoln
    ## 2412                JD 1993 Univ of Wisconsin-Madison
    ## 2413       PHD 2004 Iowa State Univ of Sci &amp; Tech
    ## 2414                     PHD 2002 Columbia University
    ## 2415            MA 1983 University Of Central Florida
    ## 2416               PHD 1996 Univ of Wisconsin-Madison
    ## 2417           PHD 2005 Russian State U of Humanities
    ## 2418                     PHD 1990 Stanford University
    ## 2419          PHD 1987 Univ of IL at Urbana-Champaign
    ## 2420              PHD 1996 Univ. Nacional de La Plata
    ## 2421                        DNP 2016 Edgewood College
    ## 2422                MS 1995 North Carolina State Univ
    ## 2423            PHD 1995 Eberhard Karls Univ Tubingen
    ## 2424                 MSN 2016 Grand Canyon University
    ## 2425                PHD 2015 Georgia State University
    ## 2426               PHD 2000 Univ of Wisconsin-Madison
    ## 2427               PHD 2018 Univ of Wisconsin-Madison
    ## 2428                   PHD 2008 Washington University
    ## 2429               EDD 2007 Univ of Wisconsin-Madison
    ## 2430                       PHD 2004 Boston University
    ## 2431             PHD 2009 Univ of Colorado at Boulder
    ## 2432                         PHD  Columbia University
    ## 2433          PHD 2005 Univ of California Los Angeles
    ## 2434                MFA 2017 Univ of California Davis
    ## 2435          PHD 1993 Univ of IL at Urbana-Champaign
    ## 2436               MSW 2006 Univ of Wisconsin-Madison
    ## 2437            PHD 2005 Univ of California San Diego
    ## 2438               PHD 2000 Univ of Wisconsin-Madison
    ## 2439            MS 1997 Univ of Michigan at Ann Arbor
    ## 2440              PHD 1998 Massachusetts Inst Of Tech
    ## 2441                   PHD 2009 Ohio State University
    ## 2442               PHD 1975 Univ of Wisconsin-Madison
    ## 2443                          MFA  University of Iowa
    ## 2444           PHD 2014 U of California-Santa Barbara
    ## 2445                     MBA 2004 Columbia University
    ## 2446                     PHD 1990 Syracuse University
    ## 2447               PHD 1976 Univ Of Minnesota-St Paul
    ## 2448                        PHD 2010 Brown University
    ## 2449              PHD 2010 University of Pennsylvania
    ## 2450                     PHD 1999 Hokkaido University
    ## 2451               PHD 1991 Univ of Wisconsin-Madison
    ## 2452               PHD 1990 Univ of Wisconsin-Madison
    ## 2453             PHD 2011 Univ of California Berkeley
    ## 2454                BA 2008 Univ of Wisconsin-Oshkosh
    ## 2455                MD 2000 Univ of Wisconsin-Madison
    ## 2456           PHD 2014 University of Texas at Austin
    ## 2457                     PHD 1985 Columbia University
    ## 2458                PHD 2005 University of Notre Dame
    ## 2459          PHD 2016 New School for General Studies
    ## 2460              MPAS 2015 Univ of Wisconsin-Madison
    ## 2461               MBA 2009 Univ of Wisconsin-Madison
    ## 2462             PHD 1985 Univ of Newcastle upon Tyne
    ## 2463           PHD 2009 U of California-Santa Barbara
    ## 2464                    PHD 2014 Princeton University
    ## 2465           PHD 1983 Univ of Massachusetts Amherst
    ## 2466           PHD 2008 Univ of Alabama at Birmingham
    ## 2467           PHD 2000 Univ of Michigan at Ann Arbor
    ## 2468             PHD 2014 Univ of Southern California
    ## 2469                      PHD 1983 Cornell University
    ## 2470                   PHD 1987 University of Georgia
    ## 2471                 PHD 1998 Old Dominion University
    ## 2472                       PHD  University of Florida
    ## 2473               PHD 1998 Univ of Wisconsin-Madison
    ## 2474                   PHD 2017 University of Chicago
    ## 2475                BS 2000 Univ of Wisconsin-Madison
    ## 2476                     PHD 1999 University of Delhi
    ## 2477                EDM 1983 Johns Hopkins University
    ## 2478                 MD 1994 Johns Hopkins University
    ## 2479                    PHD 2000 Princeton University
    ## 2480                PHD 2015 Johns Hopkins University
    ## 2481                    EDD 2007 Roosevelt University
    ## 2482                   PHD 2010 University of Wyoming
    ## 2483               PHD 2004 Rutgers State Univ-Newark
    ## 2484               PHD 1989 Univ of Wisconsin-Madison
    ## 2485           MS 2013 Concordia University Wisconsin
    ## 2486               PHD 2011 Univ of Wisconsin-Madison
    ## 2487                   PHD 2003 University of Arizona
    ## 2488               PHD 2006 Univ of Wisconsin-Madison
    ## 2489                  PHD 1985 University of Virginia
    ## 2490               MSW 2003 Univ of Wisconsin-Madison
    ## 2491               PHD 2016 Univ of Wisconsin-Madison
    ## 2492              PHD 2013 Texas A &amp; M University
    ## 2493           PHD 1999 Univ of Minnesota-Twin Cities
    ## 2494          PHD 2001 Univ of California Los Angeles
    ## 2495                      PHD 2000 University of Iowa
    ## 2496                MD 2011 Univ of Wisconsin-Madison
    ## 2497            EDD 2018 George Washington University
    ## 2498                      PHD 1998 Cornell University
    ## 2499             PHD 2004 Univ of California Berkeley
    ## 2500             PHD 2010 Universidad de La Republica
    ## 2501              PHD 1994 Massachusetts Inst Of Tech
    ## 2502             PHD 2005 Univ of California Berkeley
    ## 2503                     JD 2003 Villanova University
    ## 2504               DVM 2011 Univ of Wisconsin-Madison
    ## 2505               PHD 2014 Univ of Wisconsin-Madison
    ## 2506       PHD 2006 East China Univ of Poli &amp; Law
    ## 2507          PHD 2014 University of Nebraska-Lincoln
    ## 2508              PHD 2005 Texas A &amp; M University
    ## 2509               PHD 1999 Univ of Wisconsin-Madison
    ## 2510           MD 1999 Queen's University at Kingston
    ## 2511              PHD 1973 Carnegie-Mellon University
    ## 2512                MA 2000 Univ of Wisconsin-Madison
    ## 2513             PHD 1996 University of New Hampshire
    ## 2514                          MM 1990 Julliard School
    ## 2515           MS 2000 Univ of Wisconsin-StevensPoint
    ## 2516               EDD 2019 Univ of Wisconsin-Madison
    ## 2517                BS 1988 Univ of Wisconsin-Oshkosh
    ## 2518               PHD 1981 Rutgers State Univ-Newark
    ## 2519               PHD 2012 Univ of Wisconsin-Madison
    ## 2520                   PHD 2003 University of Chicago
    ## 2521                MD 2004 Univ of Wisconsin-Madison
    ## 2522                JD 1991 University of the Pacific
    ## 2523               PHD 1993 Univ of Wisconsin-Madison
    ## 2524               PHD 2016 Univ of Wisconsin-Madison
    ## 2525               PHD 2017 Univ of Wisconsin-Madison
    ## 2526                MD 1986 Univ of Wisconsin-Madison
    ## 2527                PHD 1990 University of Washington
    ## 2528                   PHD 2000 Ohio State University
    ## 2529               PHD 2009 Univ of Wisconsin-Madison
    ## 2530                       PHD 2002 Purdue University
    ## 2531             PHD 2005 Univ of California Berkeley
    ## 2532               PHD 2019 Univ of Wisconsin-Madison
    ## 2533                    PHD 1984 University of Oregon
    ## 2534       PHD 1997 Iowa State Univ of Sci &amp; Tech
    ## 2535               EDM 2019 Univ of Wisconsin-Madison
    ## 2536                          MA 2013 Simmons College
    ## 2537                MD 2014 Univ of Wisconsin-Madison
    ## 2538             PHD 1992 Univ of California Berkeley
    ## 2539                JD 2010 Univ of Wisconsin-Madison
    ## 2540          PHD 1999 Univ of California Los Angeles
    ## 2541       PHD 2008 Iowa State Univ of Sci &amp; Tech
    ## 2542          DVM 2016 Univ of IL at Urbana-Champaign
    ## 2543               PHD 1999 Univ of Wisconsin-Madison
    ## 2544                MS 1987 Univ of Wisconsin-Madison
    ## 2545           PHD 2010 Univ of Minnesota-Twin Cities
    ## 2546               PHD 2000 Univ of Wisconsin-Madison
    ## 2547                MA 1992 Univ of Wisconsin-Madison
    ## 2548               PHD 1988 Univ of Wisconsin-Madison
    ## 2549                JD 1992 Univ of Wisconsin-Madison
    ## 2550                   PHD 1979 University of Arizona
    ## 2551                     PHD 1962 Stanford University
    ## 2552           MD 2001 Nrtheastrn OH Univs Clg Of Med
    ## 2553               PHD 2016 Univ of Wisconsin-Madison
    ## 2554                   MFA  Univ of Wisconsin-Madison
    ## 2555           PHD 1992 University of Texas at Austin
    ## 2556                     MS 1979 Marquette University
    ## 2557       DVM 1993 Iowa State Univ of Sci &amp; Tech
    ## 2558                MS 1990 Univ of Wisconsin-Madison
    ## 2559              MSSW 1995 Univ of Wisconsin-Madison
    ## 2560                MS 1983 Univ of Wisconsin-Madison
    ## 2561                MD 2004 Univ Of NC At Chapel Hill
    ## 2562                   PHD  Univ of Wisconsin-Madison
    ## 2563                MFA 2003 Florida State University
    ## 2564                      PHD 1981 Cornell University
    ## 2565               PHD 2006 Univ of Wisconsin-Madison
    ## 2566                       JD 2018 Quinnipiac College
    ## 2567                     PHD 1995 Syracuse University
    ## 2568          BFA 2014 Bowling Green State University
    ## 2569                    PHD 2010 Marquette University
    ## 2570                 PHD 1997 University Of Rochester
    ## 2571                      PHD 2010 Cornell University
    ## 2572            PHD 1995 California Institute of Tech
    ## 2573               DMA  University of Texas at Austin
    ## 2574           PHD 2003 IN Univ-Purdue U-Indianapolis
    ## 2575            PHD 2010 Univ of California San Diego
    ## 2576                      PHD 2006 Cornell University
    ## 2577                        PHD 2004 Brown University
    ## 2578                     EDD 1970 New York University
    ## 2579               PHD 1996 Univ of Wisconsin-Madison
    ## 2580            PHARMD 2006 Univ of Wisconsin-Madison
    ## 2581              PHD 1996 Massachusetts Inst Of Tech
    ## 2582            PHARMD 2014 Univ of Wisconsin-Madison
    ## 2583              PHD 2005 University of Pennsylvania
    ## 2584             PHD 2009 Univ of California Berkeley
    ## 2585              PHD 1997 Massachusetts Inst Of Tech
    ## 2586                       MD 2001 University of Iowa
    ## 2587                PHD 1976 Johns Hopkins University
    ## 2588            MA 1997 Univ of Minnesota-Twin Cities
    ## 2589               PHD 2012 Univ of Wisconsin-Madison
    ## 2590                      PHD 2009 Harvard University
    ## 2591                      JD 2007 Stanford University
    ## 2592               DVM 2017 Univ of Wisconsin-Madison
    ## 2593           PHD 2013 Univ of Michigan at Ann Arbor
    ## 2594                     PHD 2001 Stanford University
    ## 2595           PHD 2016 Univ of Minnesota-Twin Cities
    ## 2596                         MS 2010 Edgewood College
    ## 2597             PHD 2015 Univ of Colorado at Boulder
    ## 2598                MS 2003 Univ of Wisconsin-Madison
    ## 2599               MSW 2008 Univ of Wisconsin-Madison
    ## 2600            MS 1997 Rose-Hulman Inst of Technolgy
    ## 2601                         PHD 2001 Duke University
    ## 2602              DVM 2011 University of Pennsylvania
    ## 2603                         PHD 1994 Yale University
    ## 2604                PHD 2009 University of Washington
    ## 2605                PHD 1991 Univ of California Davis
    ## 2606                      PHD 2009 Harvard University
    ## 2607                   MFA  Univ of Wisconsin-Madison
    ## 2608               PHD 2010 Univ of Wisconsin-Madison
    ## 2609               PHD 2009 Univ of Wisconsin-Madison
    ## 2610                PHD 1993 Univ Cat del Sacro Cuore
    ## 2611                                            PHD  
    ## 2612               PHD 2007 Univ of Wisconsin-Madison
    ## 2613             MD 2005 Loyola University of Chicago
    ## 2614                 PHD 2012 Northwestern University
    ## 2615               PHD 2017 Univ of Wisconsin-Madison
    ## 2616                MS 2014 Univ of Wisconsin-Madison
    ## 2617                    PHD 1996 University of Sussex
    ## 2618                 MM 1973 Indiana State University
    ## 2619                  PHD 1998 University of Delaware
    ## 2620                 PHD 2013 Northwestern University
    ## 2621                       PHD  Washington University
    ## 2622               PHD  Univ of Michigan at Ann Arbor
    ## 2623                                            PHD  
    ## 2624                    MA 1978 University of Florida
    ## 2625               PHD 2012 Univ of Wisconsin-Madison
    ## 2626                  MM 2017 Northwestern University
    ## 2627                    MA 2015 Ball State University
    ## 2628            PHD 2018 California Institute of Tech
    ## 2629                       MA 1983 University of Iowa
    ## 2630                     PHD 2007 Stanford University
    ## 2631                PHD 1989 University of Notre Dame
    ## 2632           PHD 2000 Univ of Minnesota-Twin Cities
    ## 2633                      SJD 2004 Harvard University
    ## 2634                MS 2004 Univ of Wisconsin-Madison
    ## 2635               DVM 2015 Univ Of Minnesota-St Paul
    ## 2636               PHD 1998 Univ of Wisconsin-Madison
    ## 2637               PHD 1998 Univ of Wisconsin-Madison
    ## 2638           PHD 1986 Univ of Michigan at Ann Arbor
    ## 2639                    BA 1990 Upper Iowa University
    ## 2640               DVM 2017 Michigan State University
    ## 2641                       MD 1989 University of Iowa
    ## 2642                  MSED 2015 Kent State University
    ## 2643                  PHD 1999 University of Delaware
    ## 2644                    MD 1991 Washington University
    ## 2645       PHD 2007 Iowa State Univ of Sci &amp; Tech
    ## 2646            MD 1997 SUNY Health Sci Cntr-Brooklyn
    ## 2647             PHD 2009 Washington State University
    ## 2648           PHD 1989 Univ of Michigan at Ann Arbor
    ## 2649               EDM 2016 Univ of Wisconsin-Madison
    ## 2650           PHD 2015 U of California-Santa Barbara
    ## 2651               PHD 2019 Univ of Wisconsin-Madison
    ## 2652                   PHD  Univ of Wisconsin-Madison
    ## 2653                     MFA 2011 New York University
    ## 2654             PHD 1993 Univ of Illinois at Chicago
    ## 2655                                             BS  
    ## 2656               PHD 1993 Univ of Wisconsin-Madison
    ## 2657           PHD 1994 Univ of Minnesota-Twin Cities
    ## 2658                    MA 1989 IOWA STATE UNIVERSITY
    ## 2659                 PHD 1995 Oregon State University
    ## 2660                MA 2005 Univ of Wisconsin-Madison
    ## 2661                PHD 2007 Univ of California Davis
    ## 2662               PHD 2017 Michigan State University
    ## 2663             PHD 2012 Univ of California Berkeley
    ## 2664              DVM 2015 Texas A &amp; M University
    ## 2665                     PHD 2003 Brandeis University
    ## 2666               PHD 1988 Univ of Wisconsin-Madison
    ## 2667              PHD 2013 Carnegie-Mellon University
    ## 2668            MD 1996 University of Western Ontario
    ## 2669                    PHD 1975 University of Durham
    ## 2670                MD 2006 Univ of Wisconsin-Madison
    ## 2671              PHD 1999 Massachusetts Inst Of Tech
    ## 2672                      PHD 2004 Indiana University
    ## 2673               PHD 2014 Universidade de Sao Paulo
    ## 2674                       PHD 2004 Boston University
    ## 2675            PHD 1967 Univ of California San Diego
    ## 2676                BA 1999 Univ of Wisconsin-Madison
    ## 2677            MD 2006 Univ Of Maryland At Baltimore
    ## 2678            PHD 2005 Univ of California San Diego
    ## 2679                      PHD 1983 Cornell University
    ## 2680                PHD 1999 Johns Hopkins University
    ## 2681               PHD 1980 Univ of Wisconsin-Madison
    ## 2682               MFA  University of Texas at Austin
    ## 2683               PHD 1992 Univ of Wisconsin-Madison
    ## 2684                      PHD 1987 Cornell University
    ## 2685          DNP 2014 Concordia University Wisconsin
    ## 2686                    PHD 1996 University of Kansas
    ## 2687                MS 1980 Univ of Wisconsin-Madison
    ## 2688           PHD 2015 Univ of Maryland College Park
    ## 2689                   MFA 2011 Ohio State University
    ## 2690                MD 1981 Univ of Wisconsin-Madison
    ## 2691              PHD 2020 Carnegie-Mellon University
    ## 2692                 PHD  Univ of California Berkeley
    ## 2693            PHD 2014 Univ Denis Diderot Paris VII
    ## 2694                      PHD 2012 Harvard University
    ## 2695                PHD 2002 Univ of California Davis
    ## 2696                      PHD 1982 Cornell University
    ## 2697               MD 1991 University of Pennsylvania
    ## 2698                      PHD 2006 University of Iowa
    ## 2699                   PHD 1999 University of Florida
    ## 2700                    PHD 1998 University of Oxford
    ## 2701               PHD 2006 Univ of Wisconsin-Madison
    ## 2702            PHD 2020 Rutgers St Unv-New Brunswick
    ## 2703                PHD 2016 Florida State University
    ## 2704                MD 2000 Univ of Wisconsin-Madison
    ## 2705             MD 2004 Univ of Nebraska Medical Ctr
    ## 2706               PHD 2004 Univ of Wisconsin-Madison
    ## 2707                   MFA  Univ of Wisconsin-Madison
    ## 2708            PHD 2000 Univ of Massachusetts Boston
    ## 2709               MFA 2015 Univ of Wisconsin-Madison
    ## 2710                                        PHD 2010 
    ## 2711                      JD 1979 Columbia University
    ## 2712                MA 1990 Univ of Wisconsin-Madison
    ## 2713               PHD 1989 Univ of Wisconsin-Madison
    ## 2714               PHD 2000 Univ of Missouri-Columbia
    ## 2715                 PHD 2000 Oregon State University
    ## 2716               PHD 1991 Univ of Wisconsin-Madison
    ## 2717           PHD 2007 U of California-Santa Barbara
    ## 2718             PHD 1980 Univ of California Berkeley
    ## 2719                         PHD 2005 Yale University
    ## 2720               PHD 2002 Univ Of NC At Chapel Hill
    ## 2721              PHD 1999 Massachusetts Inst Of Tech
    ## 2722               DMV 2018 Univ of Wisconsin-Madison
    ## 2723            MMS 2006 Univ of Nebraska Medical Ctr
    ## 2724                 MD 2000 Johns Hopkins University
    ## 2725                PHD 2006 University of Pittsburgh
    ## 2726               MFA  University of Texas at Austin
    ## 2727                MFA 1995 University of Pittsburgh
    ## 2728           PHD 2018 U of California-Santa Barbara
    ## 2729               PHD 2014 Univ of Wisconsin-Madison
    ## 2730             PHD 2008 Univ of California Berkeley
    ## 2731          PHD 1997 Bowling Green State University
    ## 2732          PHD 2016 Eidgenossische Tec Hoch Zurich
    ## 2733          PHD 2014 Univ Commerciale Luigi Bocconi
    ## 2734               PHD 2007 Univ of Missouri-Columbia
    ## 2735                        PHD 1996 Clark University
    ## 2736           PHD 1996 Univ of Michigan at Ann Arbor
    ## 2737                DVM 2005 Univ of California Davis
    ## 2738                    PHD 1990 Rhode Island College
    ## 2739               PHD 2012 Univ of Wisconsin-Madison
    ## 2740               PHD 2010 Univ of Wisconsin-Madison
    ## 2741                   PHD 1986 Washington University
    ## 2742               PHD 2004 Univ of Wisconsin-Madison
    ## 2743               PHD 1971 Univ of Wisconsin-Madison
    ## 2744                       PHD 2006 Temple University
    ## 2745             PHD 2007 Univ of California Berkeley
    ## 2746                    PHD 2016 University of Oxford
    ## 2747             MD 1983 Univ Of OK Health Sci Center
    ## 2748                     PHD 2018 Columbia University
    ## 2749           PHD 1990 Univ of MD-University College
    ## 2750              PHD 2013 Massachusetts Inst Of Tech
    ## 2751                     PHD 2016 Columbia University
    ## 2752             PHD 2014 Univ of California Berkeley
    ## 2753             PHD 2006 Univ of Colorado at Boulder
    ## 2754                MS 2001 Univ of Wisconsin-Madison
    ## 2755                   PHD 2006 University of Arizona
    ## 2756                    PHD 1984 Princeton University
    ## 2757            MEPD 2015 Univ of Wisconsin-La Crosse
    ## 2758              PHD 2000 Carnegie-Mellon University
    ## 2759             PHD 2011 Univ of California Berkeley
    ## 2760               PHD 2005 Univ of Wisconsin-Madison
    ## 2761               PHD 2008 Univ of Wisconsin-Madison
    ## 2762               PHD 1996 Univ of Wisconsin-Madison
    ## 2763                     PHD 2014 Stanford University
    ## 2764           EDM 2017 Grand Valley State University
    ## 2765           PHD 2017 Univ of Maryland College Park
    ## 2766            PHD 2012 California Institute of Tech
    ## 2767                         MS 2008 Regis University
    ## 2768                     PHD 1987 Tel Aviv University
    ## 2769               PHD 1995 Univ of Wisconsin-Madison
    ## 2770                MA 2010 SUNY Empire State College
    ## 2771        MS 2013 VA Polytechnic Inst &amp; State U
    ## 2772               MD 2008 Univ of Colorado at Denver
    ## 2773             PHD 1988 Univ of California Berkeley
    ## 2774                    PHD 1997 University of London
    ## 2775                PHD 2018 University of Washington
    ## 2776           PHD 1984 Univ of Minnesota-Twin Cities
    ## 2777                   PHD 2014 University of Chicago
    ## 2778               PHD 1999 Universidade de Sao Paulo
    ## 2779                   EDD 1999 University Of Houston
    ## 2780               PHD 2014 Univ of Wisconsin-Madison
    ## 2781                    PHARMD 2004 Butler University
    ## 2782                    MD 2003 Texas Tech University
    ## 2783               PHD 1996 Michigan State University
    ## 2784                   PHD 2009 University of Chicago
    ## 2785             MFA 1985 San Francisco Art Institute
    ## 2786           PHD 1993 Univ of Michigan at Ann Arbor
    ## 2787                        PHD 2008 Brown University
    ## 2788             PHD 2012 Ruprecht Karls U Heidelberg
    ## 2789               PHD 2008 Univ of Wisconsin-Madison
    ## 2790               PHD 1993 Univ of Wisconsin-Madison
    ## 2791                         PHD 2017 Duke University
    ## 2792                    MD 1969 Washington University
    ## 2793                         PHD 2006 Yale University
    ## 2794                PHD 2016 Univ of California Davis
    ## 2795           PHD 2011 Pennsylvania State University
    ## 2796                     PHD 2007 Stanford University
    ## 2797                   PHD 2008 University Of Houston
    ## 2798            PHARMD 2007 Univ of Wisconsin-Madison
    ## 2799            PHD 1979 Pennsylvania State U-Hershey
    ## 2800                PHD 2016 University of Washington
    ## 2801           MA 1978 U Rochester, Eastman Sch Music
    ## 2802              PHD 2009 University of Pennsylvania
    ## 2803                PHD 2009 University Of New Mexico
    ## 2804             PHD 2014 Univ of California Berkeley
    ## 2805                       PHD 2006 Purdue University
    ## 2806               PHD 2006 Univ of Wisconsin-Madison
    ## 2807                MFA 1984 Arizona State University
    ## 2808           MSW 1991 Univ of Michigan at Ann Arbor
    ## 2809               PHD 1999 Univ of Wisconsin-Madison
    ## 2810           PHD 2011 Univ of Michigan at Ann Arbor
    ## 2811                                        PHD 2013 
    ## 2812               PHD 2014 Univ of Wisconsin-Madison
    ## 2813           PHD 2004 Univ of Minnesota-Twin Cities
    ## 2814          PHD 2004 Australian National University
    ## 2815                   PHD 1991 University of Toronto
    ## 2816              PHD 1998 Georgia Inst of Technology
    ## 2817          PHD 2011 Univ of IL at Urbana-Champaign
    ## 2818           PHD 2006 Univ of Maryland College Park
    ## 2819                       PHD 1988 Purdue University
    ## 2820                BM 2004 Univ of Wisconsin-Madison
    ## 2821                                        EDM 2018 
    ## 2822                     PHD 1987 Stanford University
    ## 2823           PHD 1978 Pennsylvania State University
    ## 2824                      DVM 1990 Uppsala University
    ## 2825                     PHD 1988 Stanford University
    ## 2826          PHD 2005 Australian National University
    ## 2827                   PHD 1980 Ohio State University
    ## 2828                MA 2019 Univ of Wisconsin-Madison
    ## 2829               PHD 2009 Univ of Wisconsin-Madison
    ## 2830             PHD 1994 Univ of Colorado at Boulder
    ## 2831                 PHD 1997 University Of Rochester
    ## 2832                    DVM 2008 University of Guelph
    ## 2833                MS 2001 Univ of Wisconsin-Madison
    ## 2834             PHD 2007 Univ of California Berkeley
    ## 2835          PHD 2016 Univ of California Los Angeles
    ## 2836          DNP 2013 Concordia University Wisconsin
    ## 2837           PHD 1978 Univ of Michigan at Ann Arbor
    ## 2838                                        PHD 2008 
    ## 2839           PHD 1984 University of Texas at Austin
    ## 2840               MLS 2005 Univ of Wisconsin-Madison
    ## 2841               PHD 2012 Univ of Wisconsin-Madison
    ## 2842                 PHD 2006 Northwestern University
    ## 2843                PHD 2013 University of Pittsburgh
    ## 2844               PHD 2011 Univ of Wisconsin-Madison
    ## 2845           PHD 2000 U of California-Santa Barbara
    ## 2846            MD 2000 Univ of Minnesota-Twin Cities
    ## 2847                     PHD 2001 Stanford University
    ## 2848              PHD 1993 University of Pennsylvania
    ## 2849               BBA 1991 Univ of Wisconsin-Madison
    ## 2850                                             MA  
    ## 2851                PHD 1979 Eotvos Lorand University
    ## 2852               PHD 2012 Univ of Wisconsin-Madison
    ## 2853           PHD 2006 University of Texas at Austin
    ## 2854                     PHD 2018 Stanford University
    ## 2855                   PHD 2017 University of Toronto
    ## 2856           DMA 2011 Univ of Michigan at Ann Arbor
    ## 2857                                        PHD 2017 
    ## 2858                   PHD 1988 Vanderbilt University
    ## 2859            PHD 2011 Univ of California San Diego
    ## 2860               PHD 1988 Univ of Wisconsin-Madison
    ## 2861               PHD 1999 Univ of Wisconsin-Madison
    ## 2862       PHD 1986 VA Polytechnic Inst &amp; State U
    ## 2863                   PHD 2014 Irvine Valley College
    ## 2864                 MS  Univ of Wisconsin-Whitewater
    ## 2865           PHD 2006 Univ of Michigan at Ann Arbor
    ## 2866                DVM 2016 University of Queensland
    ## 2867            MA 2009 Univ of Minnesota-Twin Cities
    ## 2868          PHD 1979 Univ of IL at Urbana-Champaign
    ## 2869               DVM 1992 Univ of Wisconsin-Madison
    ## 2870                      PHD 2014 Indiana University
    ## 2871           DNP 2010 Minnesota State Univ, Mankato
    ## 2872                     JD 2008 Marquette University
    ## 2873                        MSN 2015 Edgewood College
    ## 2874                   MSN 2011 University of Phoenix
    ## 2875            PHD 1998 California Institute of Tech
    ## 2876           PHD 2014 State U of New York at Albany
    ## 2877             PHD 2005 Univ of California Berkeley
    ## 2878                         PHD 2011 Yale University
    ## 2879                MS 2018 Univ of Wisconsin-Madison
    ## 2880             MFA 1982 San Francisco Art Institute
    ## 2881                BS 1982 Univ of Wisconsin-Madison
    ## 2882               PHD 1999 Univ of Wisconsin-Madison
    ## 2883                   MD 2001 Universitat Dusseldorf
    ## 2884               PHD 1987 Univ of Wisconsin-Madison
    ## 2885             PHD 2011 Univ of California Berkeley
    ## 2886               DVM 1992 Univ of Wisconsin-Madison
    ## 2887               PHD 2006 Univ of Wisconsin-Madison
    ## 2888               PHD 1987 Univ of Wisconsin-Madison
    ## 2889                 MD 2010 Johns Hopkins University
    ## 2890                PHD 1980 University of Copenhagen
    ## 2891                MA 2016 Univ of Wisconsin-Madison
    ## 2892                                         BS 1985 
    ## 2893                      PHD 1984 Indiana University
    ## 2894               MSW 2008 Univ of Wisconsin-Madison
    ## 2895          PHD 2015 New School for General Studies
    ## 2896           PHD 2018 Univ of Minnesota-Twin Cities
    ## 2897                     PHD 2006 Germany, Fed Rep Of
    ## 2898                   PHD 2006 Fachhochschule Aachen
    ## 2899                       PHD 2005 Boston University
    ## 2900             MD 2004 Loyola University of Chicago
    ## 2901                MS 2000 Univ of Wisconsin-Madison
    ## 2902                       JD 1963 Harvard University
    ## 2903               PHD 2006 Michigan State University
    ## 2904          PHD 2018 Univ of California Los Angeles
    ## 2905             EDM 2016 Univ of Wisconsin-La Crosse
    ## 2906             PHD 2009 Univ of California Berkeley
    ## 2907               PHD 2001 Univ of Missouri-Columbia
    ## 2908                                            PHD  
    ## 2909               PHD 2001 Univ of California Irvine
    ## 2910               DVM 2006 Univ of Wisconsin-Madison
    ## 2911                                             MS  
    ## 2912           PHD 1997 Pennsylvania State University
    ## 2913           PHD 2003 Univ of Michigan at Ann Arbor
    ## 2914                                        DPT 2010 
    ## 2915                      MLA 2011 Harvard University
    ## 2916                      MS 2010 New York University
    ## 2917                     MS  Slippery Rock Univ Of PA
    ## 2918               PHD 1999 Univ of Wisconsin-Madison
    ## 2919               MSW 2008 Univ of Wisconsin-Madison
    ## 2920                MS 2012 Univ of Wisconsin-Madison
    ## 2921             MS 2011 Univ of Wisconsin-Whitewater
    ## 2922               DVM 2015 Univ of Wisconsin-Madison
    ## 2923               DVM 2008 Univ of Wisconsin-Madison
    ## 2924                JD 2001 Univ of Wisconsin-Madison
    ## 2925          PHD 2006 Univ of California Los Angeles
    ## 2926                          JD 1986 Yale University
    ## 2927                     PHD 1985 Columbia University
    ## 2928              MSN 2009 University of Pennsylvania
    ## 2929              BS 2011 Univ of Wisconsin-La Crosse
    ## 2930                MS 1989 Univ of Wisconsin-Madison
    ## 2931                       MD 1995 Harvard University
    ## 2932                PHD 2013 Univ of California Davis
    ## 2933                MS 2006 Univ of Wisconsin-Madison
    ## 2934                      PHD 1999 Cornell University
    ## 2935                     PHD 1998 Stanford University
    ## 2936             PHD 1993 Univ of California Berkeley
    ## 2937                      MFA 2007 Bennington College
    ## 2938                MD 2005 Univ of Wisconsin-Madison
    ## 2939                MS 1999 Univ of Wisconsin-Madison
    ## 2940               PHD 1985 Tech Hochschule Darmstadt
    ## 2941             BS 1974 Northern Illinois University
    ## 2942           MBA 2003 Univ of Minnesota-Twin Cities
    ## 2943                    MS  Univ of Wisconsin-Oshkosh
    ## 2944                  MD 1992 Northwestern University
    ## 2945                MS 2005 Univ of Wisconsin-Madison
    ## 2946                     PHD 1980 Columbia University
    ## 2947             PHD 1990 Univ of California Berkeley
    ## 2948                       JD 2007 Harvard University
    ## 2949                     MS 2001 Marquette University
    ## 2950                   MSN 2007 University of Phoenix
    ## 2951                   MD 2010 University of Virginia
    ## 2952               PHD 2001 Univ of Wisconsin-Madison
    ## 2953                      PHD 2011 Cornell University
    ## 2954               PHD 2000 Univ of Wisconsin-Madison
    ## 2955                         PHD 2001 Yale University
    ## 2956              PHD 2015 University of Pennsylvania
    ## 2957           PHD 1991 Univ of Minnesota-Twin Cities
    ## 2958                      PHD 2017 Harvard University
    ## 2959                 PHD 2000 University Of Rochester
    ## 2960           PHD 2000 London Sch Econ&amp; Poli Sci
    ## 2961               PHD 2003 Univ of Wisconsin-Madison
    ## 2962                      PHD 1985 Osmania University
    ## 2963                      PHD 1987 Cornell University
    ## 2964                PHD 2003 Johns Hopkins University
    ## 2965           PHD 2015 Univ of Minnesota-Twin Cities
    ## 2966                           MFA 2009 Mills College
    ## 2967            PHARMD 2002 Univ of Wisconsin-Madison
    ## 2968                   PHD 1992 University of Arizona
    ## 2969           PHD 1998 Harvard Univ Extension School
    ## 2970               PHD 1998 Univ Of Minnesota-St Paul
    ## 2971                      PHD 1987 Indiana University
    ## 2972                  MD 1996 University Of Rochester
    ## 2973                   PHD 2013 University Of Houston
    ## 2974                         PHD 2009 Duke University
    ## 2975                      PHD 2017 Harvard University
    ## 2976               PHD 2006 Univ of Wisconsin-Madison
    ## 2977             MA 2006 Univ of Tennessee, Knoxville
    ## 2978               PHD 1987 Univ of Wisconsin-Madison
    ## 2979                MA 1991 Univ of Wisconsin-Madison
    ## 2980              PHD 1992 University of Pennsylvania
    ## 2981                MA 2003 Univ of Wisconsin-Madison
    ## 2982                      PHD 1991 Cornell University
    ## 2983                    PHD 2006 Princeton University
    ## 2984                    DVM 2012 University of Guelph
    ## 2985                      PHD 2012 Harvard University
    ## 2986                   PHD 2014 University of Toronto
    ## 2987           PHD 2004 Univ of Michigan at Ann Arbor
    ## 2988               PHD 2000 Univ of Wisconsin-Madison
    ## 2989               DVM 2007 Michigan State University
    ## 2990                   DVM 2011 University of Glasgow
    ## 2991               PHD 2012 Natl Tech Univ of Ukraine
    ## 2992                      JD 1985 University Of Miami
    ## 2993                   PHD  Univ of Wisconsin-Madison
    ## 2994                MD 1985 Univ of Missouri-Columbia
    ## 2995               DVM 2016 Univ of Wisconsin-Madison
    ## 2996               PHD 1989 Univ of Wisconsin-Madison
    ## 2997               PHD 1989 Univ of Nebraska at Omaha
    ## 2998                         PHD  Columbia University
    ## 2999             PHD 2005 Univ of California Berkeley
    ## 3000               MSW 2016 Univ of Wisconsin-Madison
    ## 3001                    PHD 2013 Princeton University
    ## 3002           MD 1973 Hebrew University of Jerusalem
    ## 3003                   PHD 1998 Washington University
    ## 3004          MFA 2006 California State U- Long Beach
    ## 3005                         PHD 2006 Yale University
    ## 3006                      PHD 2000 Cornell University
    ## 3007                     PHD 1998 Stanford University
    ## 3008             PHD 2005 Univ of California Berkeley
    ## 3009                      PHD 1992 Harvard University
    ## 3010               PHD 2009 Univ of Wisconsin-Madison
    ## 3011                         PHD 2010 Yale University
    ## 3012               PHD 2015 Univ of Wisconsin-Madison
    ## 3013               PHD 2009 Univ of Wisconsin-Madison
    ## 3014              PHD 2014 University of Pennsylvania
    ## 3015             PHD 2007 Univ of Wisconsin-Milwaukee
    ## 3016               PHD 1985 Univ of Wisconsin-Madison
    ## 3017          PHD 2020 Univ of IL at Urbana-Champaign
    ## 3018                      PHD 1998 Cornell University
    ## 3019                      PHD 2009 University of Iowa
    ## 3020             PHD 2001 Univ of California Berkeley
    ## 3021              PHD 1961 Carnegie-Mellon University
    ## 3022               PHD 2009 Univ of Wisconsin-Madison
    ## 3023           MFA 1998 Univ of Michigan at Ann Arbor
    ## 3024                   PHD 2019 University of Chicago
    ## 3025               PHD 1984 Univ of Wisconsin-Madison
    ## 3026                    JD 2007 Washington University
    ## 3027          PHD 1999 Univ of IL at Urbana-Champaign
    ## 3028                       PHD 1988 Purdue University
    ## 3029                      PHD 2006 Harvard University
    ## 3030             PHD 1983 Univ of Colorado at Boulder
    ## 3031                      JD 1985 Columbia University
    ## 3032                      PHD 1986 Cornell University
    ## 3033               PHD 2005 Univ Of NC At Chapel Hill
    ## 3034                     PHD 2007 Stanford University
    ## 3035                MS 1995 Univ of Wisconsin-Madison
    ## 3036               PHD 2018 Univ of Wisconsin-Madison
    ## 3037             PHD 1996 Michigan Technological Univ
    ## 3038                      MA 1993 Bucknell University
    ## 3039             PHD 2002 Washington State University
    ## 3040                      PHD 2014 University of Utah
    ## 3041                   PHD 2012 University of Chicago
    ## 3042               PHD 1977 Univ of Wisconsin-Madison
    ## 3043          MFA 1989 Sch Of The Art Inst Of Chicago
    ## 3044          PHD 2014 Univ of California Los Angeles
    ## 3045          PHD 2018 Univ of IL at Urbana-Champaign
    ## 3046                MS 2018 Univ of Wisconsin-Madison
    ## 3047       PHD 2002 Iowa State Univ of Sci &amp; Tech
    ## 3048                     PHD 1996 New York University
    ## 3049                   PHD 1990 University of Wyoming
    ## 3050                       MD 2002 Yeshiva University
    ## 3051                         PHD 2007 SUNY at Buffalo
    ## 3052           PHD 2011 International Univ in Germany
    ## 3053                         PHD 2007 Duke University
    ## 3054                   MFA 2007 Ohio State University
    ## 3055                   MFA 2001 University of Arizona
    ## 3056               PHD 2000 Univ of Wisconsin-Madison
    ## 3057               PHD 2000 Univ of Wisconsin-Madison
    ## 3058                   PHD 1999 University of Chicago
    ## 3059               DVM 1993 Univ of Wisconsin-Madison
    ## 3060               PHD 1987 Natl Tech Univ of Ukraine
    ## 3061                PHD 2011 Florida State University
    ## 3062               PHD 2005 Univ of Wisconsin-Madison
    ## 3063               PHD 1975 Univ of Wisconsin-Madison
    ## 3064                         MFA 2009 Yale University
    ## 3065                   PHD  Univ of Wisconsin-Madison
    ## 3066           MA 2012 Univ of California Los Angeles
    ## 3067                JD 1983 Univ of Wisconsin-Madison
    ## 3068                PHD 2002 University of Pittsburgh
    ## 3069               MSN 2015 Univ of Wisconsin-Oshkosh
    ## 3070               PHD 2007 North Carolina State Univ
    ## 3071             MD 1979 Univ Of IL At Medical Center
    ## 3072             MSSW 1991 Univ of Texas at Arlington
    ## 3073                 MS 2012 Colorado School of Mines
    ## 3074                MD 1999 Univ of Wisconsin-Madison
    ## 3075               PHD 1995 Univ of Wisconsin-Madison
    ## 3076                   PHD 1996 University of Chicago
    ## 3077             PHD 2019 Univ of California Berkeley
    ## 3078                   PHD 1997 University of Chicago
    ## 3079             DVM 1989 Washington State University
    ## 3080              PHD 1988 Massachusetts Inst Of Tech
    ## 3081                     PHD 1981 Stanford University
    ## 3082                   PHD 1991 University of Chicago
    ## 3083                      MS 2010 Syracuse University
    ## 3084           BS 1986 Univ of Wisconsin-StevensPoint
    ## 3085            MS 2009 Univ of Minnesota-Twin Cities
    ## 3086           PHD 2016 Univ of Maryland College Park
    ## 3087               DVM 2016 Univ of Missouri-Columbia
    ## 3088                  PHD 2014 U of Northern Colorado
    ## 3089                    PHD 1996 Marquette University
    ## 3090               MSW 2012 Univ of Wisconsin-Madison
    ## 3091                   DVM 2004 Ohio State University
    ## 3092               DVM 2016 Univ of Wisconsin-Madison
    ## 3093               MFA 2015 Univ of Wisconsin-Madison
    ## 3094                 PHD 1988 Medical College Of Ohio
    ## 3095                      PHD 1974 Harvard University
    ## 3096              PHD 2020 Texas A &amp; M University
    ## 3097             PHD 2017 Univ of California Berkeley
    ## 3098          PHD 1985 Univ of IL at Urbana-Champaign
    ## 3099                      PHD 2006 Cornell University
    ## 3100              PHD 2000 Univ of Colorado at Denver
    ## 3101               PHD 2015 Univ of Wisconsin-Madison
    ## 3102               PHD 2007 Univ of Wisconsin-Madison
    ## 3103               PHD 1975 Univ of Wisconsin-Madison
    ## 3104                     PHD 2012 Stanford University
    ## 3105           MA 2002 Hebrew University of Jerusalem
    ## 3106              PHD 1999 Massachusetts Inst Of Tech
    ## 3107                      PHARMD 1975 SUNY at Buffalo
    ## 3108                     PHD 2008 University of Leeds
    ## 3109              DVM 2002 Texas A &amp; M University
    ## 3110            MA 2012 University of Texas at Austin
    ## 3111                 PHD 2009 Northwestern University
    ## 3112               PHD 1995 Univ of Wisconsin-Madison
    ## 3113                     PHD 2008 New York University
    ## 3114           PHD 1990 Pennsylvania State University
    ## 3115                         PHD 2017 Yale University
    ## 3116                    MTS 2002 Ave Maria University
    ## 3117               PHD 2003 Univ of Wisconsin-Madison
    ## 3118                    JD 1992 University Of Houston
    ## 3119             PHD 2014 Univ of Colorado at Boulder
    ## 3120                MFA  Univ of Arkansas-Little Rock
    ## 3121               PHD 2011 Univ of Wisconsin-Madison
    ## 3122               PHD 2007 Univ of Wisconsin-Madison
    ## 3123               PHD 1989 Univ of Wisconsin-Madison
    ## 3124          PHD 2006 Univ of California Los Angeles
    ## 3125                                        DVM 2016 
    ## 3126                   PHD 2005 Georgetown University
    ## 3127            PHD 1997 California Institute of Tech
    ## 3128          PHD 1996 University of Nebraska-Lincoln
    ## 3129                       MA 1977 Harvard University
    ## 3130                   PHD 1996 University of Chicago
    ## 3131                       PHD 2015 Boston University
    ## 3132                   PHD 2003 Vanderbilt University
    ## 3133          PHD 2000 Univ of Western Sydney, Nepean
    ## 3134                MS 2000 Univ of Wisconsin-Madison
    ## 3135                PHD 1993 Arizona State University
    ## 3136               PHD 2018 Univ of Wisconsin-Madison
    ## 3137            PHD 1990 Univ Paris Sorbonne Paris IV
    ## 3138                                        PHD 2017 
    ## 3139               MFA 2003 Univ of Wisconsin-Madison
    ## 3140                     PHD 2008 New York University
    ## 3141       PHD 2009 VA Polytechnic Inst &amp; State U
    ## 3142             PHD 2009 Washington State University
    ## 3143           PHD 2006 U of California-Santa Barbara
    ## 3144 B.ARCH 1981 Louisiana State U &amp; A&amp;M Colg
    ## 3145               PHD 2016 Univ of Wisconsin-Madison
    ## 3146                    MD 2004 Washington University
    ## 3147               DVM 2003 Univ of Wisconsin-Madison
    ## 3148                    PHD 2009 University of Kansas
    ## 3149                      PHD 2016 Harvard University
    ## 3150                       PHD 2014 Tulane University
    ## 3151               PHD 1974 Univ of Wisconsin-Madison
    ## 3152             PHD 2017 Univ of California Berkeley
    ## 3153                JD 2010 Univ of Wisconsin-Madison
    ## 3154              BFA 1995 Texas Christian University
    ## 3155                     PHD 2016 American University
    ## 3156                    MD 1992 Ohio State University
    ## 3157                       PHD 1993 Purdue University
    ## 3158                                        PHD 2014 
    ## 3159                         BA 1974 Drake University
    ## 3160                      JD 2005 American University
    ## 3161               PHD 2006 Univ of Wisconsin-Madison
    ## 3162           PHD 1988 Univ of Minnesota-Twin Cities
    ## 3163                 MS 2002 University of Louisville
    ## 3164           PHD 1988 Univ of Minnesota-Twin Cities
    ## 3165                    PHD 2017 Princeton University
    ## 3166                      PHD 1984 Cornell University
    ## 3167             BFA 1982 Univ of Wisconsin-Milwaukee
    ## 3168                   MFA  Univ of Wisconsin-Madison
    ## 3169             PHD 2009 Univ of California Berkeley
    ## 3170          PHD 1983 U Rochester, Eastman Sch Music
    ## 3171             PHD 2016 Florida Inst. Of Technology
    ## 3172            MD 1988 Univ Of TX Med Branch-Galvest
    ## 3173                         PHD 2006 Duke University
    ## 3174           MA 2008 Lviv National Univ Ivan Franko
    ## 3175                                             ME  
    ## 3176               PHD 1994 Univ of Wisconsin-Madison
    ## 3177             PHD 2004 Univ of California Berkeley
    ## 3178                    PHD 2007 Princeton University
    ## 3179              PHD 1999 Massachusetts Inst Of Tech
    ## 3180                      PHD 1986 Harvard University
    ## 3181                   PHD 1995 Washington University
    ## 3182               PHD 2018 Univ of Wisconsin-Madison
    ## 3183                         MSN 2004 Phoenix College
    ## 3184               PHD 2000 Univ of Wisconsin-Madison
    ## 3185                                            PHD  
    ## 3186               PHD 2015 Univ of Wisconsin-Madison
    ## 3187           MD 2005 Mt Sinai School of Med of CUNY
    ## 3188           PHD 2020 Univ of Minnesota-Twin Cities
    ## 3189               PHD 2011 Univ of Wisconsin-Madison
    ## 3190                     PHD 2008 Syracuse University
    ## 3191                     PHD 1973 Columbia University
    ## 3192                                        PHD 2009 
    ## 3193           PHD 2017 Univ of Michigan at Ann Arbor
    ## 3194                    PHD 2006 Marquette University
    ## 3195               PHD 1980 Univ of Wisconsin-Madison
    ## 3196               PHD 2012 Univ of Wisconsin-Madison
    ## 3197               PHD 1996 Univ of Wisconsin-Madison
    ## 3198               MBA 2003 Univ of Wisconsin-Madison
    ## 3199                      PHD 1998 Cornell University
    ## 3200                        MPH 2009 Tufts University
    ## 3201                       MA 2012 Middlebury College
    ## 3202               PHD 2009 Univ of Wisconsin-Madison
    ## 3203               PHD 1976 Michigan State University
    ## 3204                  PHD 1985 University of Virginia
    ## 3205           PHD 2010 Nat Inst for Academic Degrees
    ## 3206                     PHD 1999 University of Tokyo
    ## 3207                   PHD 1992 Vanderbilt University
    ## 3208                    MD 1980 University of Chicago
    ## 3209                         PHD 1988 Yale University
    ## 3210               PHD 2015 Univ of Wisconsin-Madison
    ## 3211              PHD 1983 Carnegie-Mellon University
    ## 3212               MBA 1981 Univ of Wisconsin-Madison
    ## 3213                   DVM 2002 University of Georgia
    ## 3214                        PHD 1999 Emory University
    ## 3215                                          OQUAL  
    ## 3216      PHD 1999 Grad Sch &amp; Univ Center Of Cuny
    ## 3217                PHD 2005 University of Washington
    ## 3218               PHD 2019 Univ of Wisconsin-Madison
    ## 3219             PHD 2006 Univ of California Berkeley
    ## 3220                PHD 2019 University of Notre Dame
    ## 3221                   PHD 1983 Washington University
    ## 3222            PHD 2002 Univ of Tennessee, Knoxville
    ## 3223                   PHD 1995 University of Chicago
    ## 3224                     PHD 2010 Stanford University
    ## 3225                          JD 2007 Yale University
    ## 3226                        PHD 1997 Tufts University
    ## 3227               DVM 2004 Universidade de Sao Paulo
    ## 3228               MSW 2012 Univ of Wisconsin-Madison
    ## 3229             PHD 1998 Univ of MD Baltimore County
    ## 3230                JD 1978 Univ of Wisconsin-Madison
    ## 3231                   PHD 2009 University of Toronto
    ## 3232                     PHD 2005 Stanford University
    ## 3233               PHD 2014 Univ Of NC At Chapel Hill
    ## 3234                                         M.ARCH  
    ## 3235                         PHD 2008 Duke University
    ## 3236              PHD 2020 Georgia Inst of Technology
    ## 3237               PHD 2001 Univ of Wisconsin-Madison
    ## 3238       PHD 1993 Iowa State Univ of Sci &amp; Tech
    ## 3239               MAT 1995 Univ of Wisconsin-Madison
    ## 3240               PHD 2012 Univ of Wisconsin-Madison
    ## 3241             AUD 2006 Central Michigan University
    ## 3242            MA 1999 New England Cnsrvtry Of Music
    ## 3243                JD 2009 Univ of Wisconsin-Madison
    ## 3244                      PHD 1987 Cornell University
    ## 3245             PHD 2012 Univ of Southern California
    ## 3246                PHD 2002 University of Washington
    ## 3247           MS 2012 Concordia University Wisconsin
    ## 3248                   PHD 2015 University of Florida
    ## 3249            MM 2000 Univ of Michigan at Ann Arbor
    ## 3250            DVM 2002 Instituto Unificado Paulista
    ## 3251               PHD 2005 Univ of Wisconsin-Madison
    ## 3252            PHARMD 2004 Univ Of NC At Chapel Hill
    ## 3253               PHD 1993 Univ of Wisconsin-Madison
    ## 3254           MD 1992 Univ Med si Farm-Carol Davilla
    ## 3255                PHD 1966 Yokohama City University
    ## 3256           PHD 2002 U of California-Santa Barbara
    ## 3257           PHD 1981 University of Texas at Austin
    ## 3258          PHD 1982 Univ of IL at Urbana-Champaign
    ## 3259               PHD 2014 Univ of Wisconsin-Madison
    ## 3260                     PHD 1999 Columbia University
    ## 3261                                        DVM 2005 
    ## 3262           PHD 2017 Univ of Minnesota-Twin Cities
    ## 3263                DS 2010 ROCKY MOUNTAIN UNIVERSITY
    ## 3264                MS 1988 Univ of Wisconsin-Madison
    ## 3265                PHD 2013 Univ of California Davis
    ## 3266           PHD 1992 Univ of Michigan at Ann Arbor
    ## 3267               PHD 2011 Univ of Wisconsin-Madison
    ## 3268             MD 2010 Rutgers St Unv-New Brunswick
    ## 3269            PHD 2015 California Institute of Tech
    ## 3270               PHD 2001 Univ of Wisconsin-Madison
    ## 3271                   PHD  Univ of Wisconsin-Madison
    ## 3272           PHD 1998 University of Texas at Austin
    ## 3273                         PHD 1974 Yale University
    ## 3274               PHD 1992 Univ of Wisconsin-Madison
    ## 3275               PHD 1992 Michigan State University
    ## 3276           PHD 2013 Univ of Michigan at Ann Arbor
    ## 3277               PHD 1999 Univ of Wisconsin-Madison
    ## 3278               PHD 2013 Michigan State University
    ## 3279            MS 2012 Univ of Minnesota-Twin Cities
    ## 3280               PHD 2001 Univ Of Minnesota-St Paul
    ## 3281            PHD 1992 Univ of Tennessee, Knoxville
    ## 3282           PHD 2018 Univ of Michigan at Ann Arbor
    ## 3283                  MS  Univ of Wisconsin-Milwaukee
    ## 3284               PHD 2004 Univ of Wisconsin-Madison
    ## 3285                     PHD 2008 University of Akron
    ## 3286            MD 2011 SUNY Health Sci Cntr-Syracuse
    ## 3287              PHD 1988 University of Pennsylvania
    ## 3288               PHD 2008 North Carolina State Univ
    ## 3289              PHD 1981 Massachusetts Inst Of Tech
    ## 3290                                        DVM 2014 
    ## 3291               PHD 1985 Univ Of NC At Chapel Hill
    ## 3292               PHD 2004 Univ of Wisconsin-Madison
    ## 3293                 PHD 1995 Northwestern University
    ## 3294            PHD 2012 Univ of California San Diego
    ## 3295                        PHD 2017 Emory University
    ## 3296               PHD 1994 Univ Of Minnesota-St Paul
    ## 3297               PHD 2014 Univ of Wisconsin-Madison
    ## 3298                         PHD 2001 Duke University
    ## 3299                    PHD 1985 Princeton University
    ## 3300                BS 2014 Univ of Wisconsin-Madison
    ## 3301                       EDD 2012 Walden University
    ## 3302                MA 1988 Univ of Wisconsin-Madison
    ## 3303                JD 1989 Univ of Wisconsin-Madison
    ## 3304               PHD 2006 Univ of Wisconsin-Madison
    ## 3305                                            PHD  
    ## 3306               PHD 1999 Univ of Wisconsin-Madison
    ## 3307             PHD 2008 Univ of California Berkeley
    ## 3308              DVM 2012 University of Saskatchewan
    ## 3309             JD 1979 University of Texas, Houston
    ## 3310                    PHD 1997 University of Ottawa
    ## 3311                      PHD 2009 Indiana University
    ## 3312             DVM 2016 St George's Univ Sch of Med
    ## 3313                BS 1995 Univ of Wisconsin-Madison
    ## 3314                      PHD 2010 Cornell University
    ## 3315              MS 2008 Eastern Illinois University
    ## 3316              PHD 1973 University of Pennsylvania
    ## 3317                         PHD 2012 Duke University
    ## 3318                MS 2013 Univ of Wisconsin-Madison
    ## 3319                PHD 1989 Univ degli Studi di Pisa
    ## 3320               MLS 2013 Univ of Wisconsin-Madison
    ## 3321               PHD 1997 Univ Of NC At Chapel Hill
    ## 3322                    PHD 1997 University of London
    ## 3323                      PHD 1982 Cornell University
    ## 3324             PHD 2012 Univ of California Berkeley
    ## 3325              PHD 2011 Univ of Alabama-Tuscaloosa
    ## 3326               PHD 2017 Univ of Wisconsin-Madison
    ## 3327                     PHD 2020 Stanford University
    ## 3328                PHD 2003 Johns Hopkins University
    ## 3329                      PHD 1997 Cornell University
    ## 3330                MS 2006 Univ of Wisconsin-Madison
    ## 3331                      PHD 1997 Harvard University
    ## 3332               MSW 2014 Univ of Wisconsin-Madison
    ## 3333                      PHD 1998 Cornell University
    ## 3334               EDD 2004 Univ of Wisconsin-Madison
    ## 3335              PHD 2008 Texas A &amp; M University
    ## 3336               PHD 2017 Univ of Wisconsin-Madison
    ## 3337                          MAED  DePaul University
    ## 3338               PHD 1986 Colorado State University
    ## 3339                 PHD 1990 Northwestern University
    ## 3340                 PHD 1996 Northwestern University
    ## 3341             PHD 2012 Univ of Colorado at Boulder
    ## 3342                        JD 2003 DePaul University
    ## 3343          PHD 2000 Univ of IL at Urbana-Champaign
    ## 3344                        MAT 2008 Edgewood College
    ## 3345               MFA 1999 Univ of Wisconsin-Madison
    ## 3346                      JD 1963 New York Law School
    ## 3347                MS 2000 Univ of Wisconsin-Madison
    ## 3348               PHD 2009 Univ of Wisconsin-Madison
    ## 3349                                  PHD 2013 France
    ## 3350                  DVM 1998 University of Montreal
    ## 3351                JD 2008 Univ of Wisconsin-Madison
    ## 3352               EDM 2018 Univ of Wisconsin-Madison
    ## 3353                 PHD  Univ of California Berkeley
    ## 3354                JD 2020 Univ of Wisconsin-Madison
    ## 3355             PHD 1992 Univ of California Berkeley
    ## 3356                   PHD 1985 University of Georgia
    ## 3357                      PHD 1990 Cornell University
    ## 3358              MS 1986 Univ of California Berkeley
    ## 3359              PHD 2017 Massachusetts Inst Of Tech
    ## 3360               PHD 1990 Univ of Wisconsin-Madison
    ## 3361                        PHD 1983 Brown University
    ## 3362                      PHD 2014 University of Iowa
    ## 3363                   PHD 1984 University of Florida
    ## 3364                      EDM 2013 Clemson University
    ## 3365               PHD 2012 Univ of Wisconsin-Madison
    ## 3366             PHD 1989 U de Santiago de Compostela
    ## 3367                     PHD 2017 Columbia University
    ## 3368             PHD 2007 Univ of California Berkeley
    ## 3369                      PHD 2020 Cornell University
    ## 3370              DVM 1984 University of Saskatchewan
    ## 3371              MSSW 2007 Univ of Wisconsin-Madison
    ## 3372                MS 2008 Univ of Wisconsin-Madison
    ## 3373        PHD 2004 Budapest Univ of Tech &amp; Econ
    ## 3374           PHD 1980 Univ of Michigan at Ann Arbor
    ## 3375             MFA 1977 Conserv Nat Arts et Metiers
    ## 3376                         MFA 2006 Yale University
    ## 3377                                            DVM  
    ## 3378              MLIS 1997 Univ of Wisconsin-Madison
    ## 3379                PHD 1996 Arizona State University
    ## 3380               PHD 1995 Michigan State University
    ## 3381                     PHD 1992 Stanford University
    ## 3382                MD 2002 Univ of Wisconsin-Madison
    ## 3383                PHD 1984 Univ of California Davis
    ## 3384              PHD 2014 Massachusetts Inst Of Tech
    ## 3385                         MSN 2014 Duke University
    ## 3386                   PHD 1999 University of Chicago
    ## 3387                PHD 2015 Univ of California Davis
    ## 3388                          PHD 2007 Ireland (Eire)
    ## 3389               PHD 2018 Univ of Wisconsin-Madison
    ## 3390                JD 1990 Univ of Wisconsin-Madison
    ## 3391                JD 2006 Univ of Wisconsin-Madison
    ## 3392          PHD 1998 Univ of IL at Urbana-Champaign
    ## 3393                     JD 2007 University of Oregon
    ## 3394               PHD 1988 Univ of Wisconsin-Madison
    ## 3395             PHD 2009 Univ of California Berkeley
    ## 3396                       PHD 1999 McGill University
    ## 3397                      PHD 2017 Harvard University
    ## 3398                             PHD  Rush University
    ## 3399             PHD 1986 Univ of Colorado at Boulder
    ## 3400                          MM 1977 Yale University
    ## 3401               PHD 2011 Rutgers State Univ-Newark
    ## 3402             PHD 2006 Universidad de La Republica
    ## 3403               PHD 1998 Univ of Wisconsin-Madison
    ## 3404                  PHD 1995 University of Kentucky
    ## 3405                          JD 2018 Yale University
    ## 3406                   PHD 2004 University of Chicago
    ## 3407                JD 1999 Univ of Wisconsin-Madison
    ## 3408                      PHD 2001 Cornell University
    ## 3409                       PHD 1991 Purdue University
    ## 3410                      AUD 2009 Indiana University
    ## 3411               MFA 2000 Univ of Wisconsin-Madison
    ## 3412                PHD 2009 University Of New Mexico
    ## 3413                 PHD 1991 University of Hyderabad
    ## 3414             PHD 2017 Univ of California Berkeley
    ## 3415               PHD 1992 Univ of Wisconsin-Madison
    ## 3416               PHD 1989 Univ of Wisconsin-Madison
    ## 3417            PHD 2013 California Institute of Tech
    ## 3418                MBA  Univ of Wisconsin-Whitewater
    ## 3419               DVM 2003 Univ of Wisconsin-Madison
    ## 3420           PHD 2013 Univ of Minnesota-Twin Cities
    ## 3421                 PHD 1967 Northwestern University
    ## 3422                         PHD 2003 SUNY at Buffalo
    ## 3423               MBA 2017 Univ of Wisconsin-Madison
    ## 3424               PHD 2010 Univ of Wisconsin-Madison
    ## 3425                PHD 1990 Johns Hopkins University
    ## 3426           PHD 2019 University of Texas at Austin
    ## 3427                PHD 2002 University of Washington
    ## 3428                JD 1978 Univ of Wisconsin-Madison
    ## 3429                MS 1986 Univ of Wisconsin-Madison
    ## 3430          PHARMD 1995 Univ of Illinois at Chicago
    ## 3431               DVM 2003 Univ of Wisconsin-Madison
    ## 3432          PHD 2012 Univ of California Los Angeles
    ## 3433               MSN 2000 Univ of Wisconsin-Madison
    ## 3434                  PHD 2001 University of Kentucky
    ## 3435                      JD 1995 Brooklyn Law School
    ## 3436                    JD 1994 Valparaiso University
    ## 3437          PHD 2001 Univ of IL at Urbana-Champaign
    ## 3438           PHD 2001 Univ of Michigan at Ann Arbor
    ## 3439             MS 2010 Univ of Wisconsin-Whitewater
    ## 3440                                         M.ARCH  
    ## 3441                      PHD 2016 Indiana University
    ## 3442                  PHD 2019 University of Oklahoma
    ## 3443                PHD 2018 Univ of California Davis
    ## 3444               PHD 2020 Univ of Wisconsin-Madison
    ## 3445                      PHD 2006 Indiana University
    ## 3446                PHD 2017 Colorado School of Mines
    ## 3447           MFA 1994 University of Texas at Austin
    ## 3448                BA 2013 Univ of Wisconsin-Madison
    ## 3449            PHARMD 2016 Univ of Wisconsin-Madison
    ## 3450               PHD 2011 Univ of Wisconsin-Madison
    ## 3451                      MD 2011 Aga Khan University
    ## 3452          PHD 1987 Univ of IL at Urbana-Champaign
    ## 3453                 PHD 1990 University of Groningen
    ## 3454                  MD 1997 Northwestern University
    ## 3455            PHARMD 1993 Univ of Wisconsin-Madison
    ## 3456                         PHD 2016 Yale University
    ## 3457                     PHD 2014 Columbia University
    ## 3458              PHD 1989 Massachusetts Inst Of Tech
    ## 3459               MFA 2004 SUNY College at Brockport
    ## 3460                   PHD 1986 University of Chicago
    ## 3461               DVM 2008 Michigan State University
    ## 3462                    PHD 1988 Princeton University
    ## 3463                 PHD 1999 Northwestern University
    ## 3464                 DNP 2012 Univ of Wisconsin-Stout
    ## 3465               DVM 2007 Univ of Wisconsin-Madison
    ## 3466                MS 2007 Univ of Wisconsin-Madison
    ## 3467                     PHD 2010 New York University
    ## 3468                  MS  Western Illinois University
    ## 3469                JD 1975 Univ of Wisconsin-Madison
    ## 3470                MS 1992 Univ of Wisconsin-Madison
    ## 3471          PHD 2011 University of Nebraska-Lincoln
    ## 3472              DRPH 2010 Univ of Wisconsin-Madison
    ## 3473           PHD 2013 Univ of Michigan at Ann Arbor
    ## 3474               PHD 2002 Univ of Wisconsin-Madison
    ## 3475           PHD 1985 Univ of Michigan at Ann Arbor
    ## 3476                       PHD 2012 Purdue University
    ## 3477                                        PHD 2012 
    ## 3478                         PHD 2015 Yale University
    ## 3479             PHD 2013 Univ of Southern California
    ## 3480               PHD 2006 Univ of Wisconsin-Madison
    ## 3481           PHD 2002 U of California San Francisco
    ## 3482            MA 1995 University of Hawaii at Manoa
    ## 3483                   PHD 2014 University of Chicago
    ## 3484                         PHD 2015 Yale University
    ## 3485          PHD 2015 Univ of IL at Urbana-Champaign
    ## 3486              PHD 2005 Georgia Inst of Technology
    ## 3487                   PHD 2008 Ohio State University
    ## 3488                         PHD 2009 Duke University
    ## 3489             PHD 1992 Univ of California Berkeley
    ## 3490               PHD 2012 Univ of Wisconsin-Madison
    ## 3491                 PHD  Univ of California Berkeley
    ## 3492                MPA  Univ of Wisconsin-Whitewater
    ## 3493                                        PHD 2011 
    ## 3494          PHD 1997 Padagogische Hochsch Gottingen
    ## 3495               PHD 1999 Univ of Wisconsin-Madison
    ## 3496               PHD 2002 Univ of Wisconsin-Madison
    ## 3497                         PHD 2016 Yale University
    ## 3498                PHD 2014 University of Pittsburgh
    ## 3499                      PHD 1989 University of Iowa
    ## 3500                MD 1985 Univ of Wisconsin-Madison
    ## 3501               PHD 2017 Univ of Wisconsin-Madison
    ## 3502               PHD 2013 Univ of Wisconsin-Madison
    ## 3503                         PHD 1992 Yale University
    ## 3504                         PHD 1992 Yale University
    ## 3505            MD 2010 Univ Of TX Med Branch-Galvest
    ## 3506                PHD 1997 University of Washington
    ## 3507               PHD 1990 Univ of Wisconsin-Madison
    ## 3508               PHD 2020 Univ of Missouri-Columbia
    ## 3509                     MFA 2008 University of Idaho
    ## 3510            PHD 2003 Univ of California San Diego
    ## 3511             DS 2005 California Institute of Tech
    ## 3512                      PHD 2012 Harvard University
    ## 3513               PHD 2016 Univ of Wisconsin-Madison
    ## 3514             PHD 2013 Univ of California Berkeley
    ## 3515                     PHD 2009 Stanford University
    ## 3516                                            PHD  
    ## 3517           PHD 1985 Univ of Michigan at Ann Arbor
    ## 3518               PHD 1992 Univ of Wisconsin-Madison
    ## 3519            JD 1983 University of Texas at Austin
    ## 3520             PHD 1978 Univ of California Berkeley
    ## 3521                     PHD 2013 Columbia University
    ## 3522             PHD 1979 Univ of California Berkeley
    ## 3523             PHD 2005 Univ of California Berkeley
    ## 3524           PHD 1979 VA Commonwealth Univ-Hlth Sci
    ## 3525               PHD 2006 Univ of Wisconsin-Madison
    ## 3526               PHD 1996 Univ of Wisconsin-Madison
    ## 3527             PHD 2009 Univ of California Berkeley
    ## 3528           PHD 2011 University of Texas at Austin
    ## 3529                        PHD 1978 Lunds University
    ## 3530           PHD 1994 Univ of Massachusetts Amherst
    ## 3531             PHD 1988 Univ of California Berkeley
    ## 3532               PHD 1999 Univ of Wisconsin-Madison
    ## 3533              PHD 1998 Texas A &amp; M University
    ## 3534               PHD 2016 Univ of Wisconsin-Madison
    ## 3535                   PHD 2015 Vanderbilt University
    ## 3536                         PHD 2006 Yale University
    ## 3537          PHD 2016 University of Nebraska-Lincoln
    ## 3538          PHD 2014 Univ of California Los Angeles
    ## 3539          PHD 1979 Univ of IL at Urbana-Champaign
    ## 3540                 PHD 2014 George Mason University
    ## 3541               MBA 1969 Univ of Wisconsin-Madison
    ## 3542                EDD 2017 Univ of Minnesota-Duluth
    ## 3543              PHD 1983 Massachusetts Inst Of Tech
    ## 3544                PHD 2013 Johns Hopkins University
    ## 3545                       PHD 1980 Purdue University
    ## 3546                      PHD 1995 Notre Dame College
    ## 3547               PHD 2004 Univ of Wisconsin-Madison
    ## 3548                    PHD 2004 University of Oxford
    ## 3549                       PHD 2010 Purdue University
    ## 3550             PHD 1998 Western Michigan University
    ## 3551              DVM 2017 Texas A &amp; M University
    ## 3552                      PHD 2015 Harvard University
    ## 3553                      PHD 2014 Cornell University
    ## 3554           PHD 2000 Univ of Michigan at Ann Arbor
    ## 3555             DNS 2017 Univ of Wisconsin-Milwaukee
    ## 3556                    PHD 2005 University of Oxford
    ## 3557            PHD 2015 California Institute of Tech
    ## 3558            PHD 2005 California Institute of Tech
    ## 3559                 MFA 2013 George Mason University
    ## 3560               PHD 2002 Univ of Wisconsin-Madison
    ## 3561                  MS  Univ of Wisconsin-Milwaukee
    ## 3562              PHD 1992 Texas Christian University
    ## 3563               PHD 1993 Univ of Wisconsin-Madison
    ## 3564                MM 2018 Manhattan School Of Music
    ## 3565          JD 1992 Washington &amp; Lee University
    ## 3566               MA 2016 University Of South Dakota
    ## 3567                PHD 1992 University of Washington
    ## 3568               PHD 1983 Univ of Wisconsin-Madison
    ## 3569                     PHD 2005 Columbia University
    ## 3570                MA 2008 Univ of Wisconsin-Madison
    ## 3571                PHD 1997 University of Washington
    ## 3572                  PHD 2015 University of Virginia
    ## 3573         MSED 2019 Concordia University Wisconsin
    ## 3574               DPT 2015 Univ of Wisconsin-Madison
    ## 3575               PHD 2017 Univ of Wisconsin-Madison
    ## 3576                    PHD 2002 University of London
    ## 3577                        PHD 1999 Brown University
    ## 3578            PHD 2016 Univ of California San Diego
    ## 3579             PHD 2014 Univ of Wisconsin-Milwaukee
    ## 3580                PHD 2001 Arizona State University
    ## 3581                  MD 2004 Meharry Medical College
    ## 3582       MA 2005 Walsh Col Accountant &amp; Bus Adm
    ## 3583                   PHD 2001 University of Chicago
    ## 3584                MS 2000 Univ of Wisconsin-Madison
    ## 3585                    JD 1975 Georgetown University
    ## 3586          PHD 2019 Univ of IL at Urbana-Champaign
    ## 3587                                        MMS 2007 
    ## 3588           PHD 2020 Univ of Michigan at Ann Arbor
    ## 3589                         MSW 2005 Simmons College
    ## 3590                MD 1997 Univ of Wisconsin-Madison
    ## 3591                JD 2017 Univ of Wisconsin-Madison
    ## 3592               PHD 1999 Univ of Wisconsin-Madison
    ## 3593           PHD 1987 Univ of Michigan at Ann Arbor
    ## 3594                       MSN 2013 Walden University
    ## 3595            MBA 2011 Univ of Wisconsin-Eau Claire
    ## 3596                      PHD 2006 Indiana University
    ## 3597               PHD 1990 Univ of Wisconsin-Madison
    ## 3598               PHD 1994 Univ of Wisconsin-Madison
    ## 3599          PHD 2005 Univ of California Los Angeles
    ## 3600                                            PHD  
    ## 3601               PHD 2011 Univ of Wisconsin-Madison
    ## 3602                   LLM 1997 Georgetown University
    ## 3603                   PHD 2015 University of Toronto
    ## 3604                    PHD 1987 University of London
    ## 3605           PHD 2005 University of Texas at Austin
    ## 3606              MACC 2020 Univ of Wisconsin-Madison
    ## 3607               PHD 1996 Univ of Wisconsin-Madison
    ## 3608               PHD 2000 Univ of Wisconsin-Madison
    ## 3609           PHD 1996 Univ of Michigan at Ann Arbor
    ## 3610               PHD 2009 Univ Of NC At Chapel Hill
    ## 3611               PHD 2010 North Carolina State Univ
    ## 3612               PHD 1989 Univ Of NC At Chapel Hill
    ## 3613                      PHD 1965 Harvard University
    ## 3614               PHD 2005 Univ of Wisconsin-Madison
    ## 3615                   PHD 2007 University of Arizona
    ## 3616                MS 2004 Univ of Wisconsin-Madison
    ## 3617                    PHD 2013 Princeton University
    ## 3618                        PHD 2002 Emory University
    ## 3619                PHD 1970 Johns Hopkins University
    ## 3620           PHD 1986 Univ of Minnesota-Twin Cities
    ## 3621                PHD 1984 University of Queensland
    ## 3622                    JD 2006 Washington University
    ## 3623                      EDD 2006 Harvard University
    ## 3624                MS 2020 Univ of Wisconsin-Madison
    ## 3625                      PHD 2016 Cornell University
    ## 3626              PHD 1999 Massachusetts Inst Of Tech
    ## 3627           JD 2009 Univ of California Los Angeles
    ## 3628                      PHD 1970 Harvard University
    ## 3629                  MS 2000 University of Edinburgh
    ## 3630                PHD 2005 University of Washington
    ## 3631               PHD 1997 Rutgers State Univ-Newark
    ## 3632          PHD 2013 Univ of California Los Angeles
    ## 3633                PHD 1993 Johns Hopkins University
    ## 3634              PHD 2015 Georgia Inst of Technology
    ## 3635                      PHD 1999 University of Iowa
    ## 3636             PHD 2014 Chinese Academy of Sciences
    ## 3637                          JD 2006 Yale University
    ## 3638               PHD 2006 Univ Of NC At Chapel Hill
    ## 3639               PHD 2003 Univ Of NC At Chapel Hill
    ## 3640               PHD 2016 Univ of Wisconsin-Madison
    ## 3641             PHD 1981 Univ of California Berkeley
    ## 3642              PHD 2006 Case Western Reserve Univ.
    ## 3643                  PHD  University of Pennsylvania
    ## 3644           PHD 1995 Univ of Maryland College Park
    ## 3645                         PHD 2016 Duke University
    ## 3646                   PHD  Univ of Wisconsin-Madison
    ## 3647                      PHD 1991 University of Iowa
    ## 3648                     PHD 2003 Stanford University
    ## 3649               PHD 2000 Univ Of NC At Chapel Hill
    ## 3650               PHD  Univ of Maryland College Park
    ## 3651               PHD 1991 North Carolina State Univ
    ## 3652               PHD 1986 Univ of Wisconsin-Madison
    ## 3653             PHD 1988 Univ of California Berkeley
    ## 3654           PHD 1973 Univ of Michigan at Ann Arbor
    ## 3655            PHD 2002 California Institute of Tech
    ## 3656              MLIS 2008 Univ of Wisconsin-Madison
    ## 3657               PHD 1981 Michigan State University
    ## 3658                     PHD 1993 Columbia University
    ## 3659                JD 2005 Univ of Wisconsin-Madison
    ## 3660           PHD 1997 Univ of Michigan at Ann Arbor
    ## 3661              PHD 1989 University of Pennsylvania
    ## 3662                PHD 2010 University of Washington
    ## 3663               PHD 1995 Univ of Wisconsin-Madison
    ## 3664                       PHD 1994 Temple University
    ## 3665          PHD 2006 Univ of IL at Urbana-Champaign
    ## 3666                   PHD 1991 Ohio State University
    ## 3667           PHD 2003 Univ of Michigan at Ann Arbor
    ## 3668                     PHD 2005 Stanford University
    ## 3669              PHD 2017 Massachusetts Inst Of Tech
    ## 3670                     PHD 2009 Stanford University
    ## 3671                      PHD 2015 Harvard University
    ## 3672                  PHD  Massachusetts Inst Of Tech
    ## 3673                MS 1998 Naval Postgraduate School
    ## 3674                     PHD 2018 Stanford University
    ## 3675                MD 1990 Univ of Wisconsin-Madison
    ## 3676               PHD 2005 Univ of Wisconsin-Madison
    ## 3677       PHD 2011 Iowa State Univ of Sci &amp; Tech
    ## 3678             MA 1999 Northern Illinois University
    ## 3679             PHD 1999 Univ of California Berkeley
    ## 3680                MD 2013 Univ of Wisconsin-Madison
    ## 3681            MD 1996 Univ of Alabama at Birmingham
    ## 3682              PHD 2008 Carnegie-Mellon University
    ## 3683                      PHD 2015 Cornell University
    ## 3684                         MD 1982 Tufts University
    ## 3685               PHD 1968 Univ of Wisconsin-Madison
    ## 3686               PHD 1996 University of Connecticut
    ## 3687               PHD 2015 Univ of Wisconsin-Madison
    ## 3688               PHD 1999 Univ of Wisconsin-Madison
    ## 3689              PHD 2015 Massachusetts Inst Of Tech
    ## 3690            PHD 2015 Univ of California Riverside
    ## 3691               PHD 2000 Univ Of NC At Chapel Hill
    ## 3692       PHD 2007 Texas A &amp; M Univ At Galveston
    ## 3693              PHD 2015 University of Pennsylvania
    ## 3694             PHD 2020 Univ of California Berkeley
    ## 3695            PHD 1992 Univ of California San Diego
    ## 3696            PHD 2014 Macau Univ of Sci &amp; Tech
    ## 3697              PHD 2001 University of Pennsylvania
    ## 3698            PHD 2015 California Institute of Tech
    ## 3699                          PHD  University of Iowa
    ## 3700                    MS  Univ of Wisconsin-Madison
    ## 3701              PHD 2014 University of Pennsylvania
    ## 3702                  PHD 2009 Polytechnic University
    ## 3703               PHD 2002 Univ Of NC At Chapel Hill
    ## 3704                       PHD 2017 Purdue University
    ## 3705                   PHD 2014 University of Georgia
    ## 3706                   PHD  Univ of Wisconsin-Madison
    ## 3707                PHD 1997 University of Washington
    ## 3708                      PHD 2020 Cornell University
    ## 3709           PHD 1995 North Dakota State University
    ## 3710                   PHD 2007 Ohio State University
    ## 3711               PHD 2008 Univ Of Missouri-St Louis
    ## 3712           PHD 2000 Univ of Michigan at Ann Arbor
    ## 3713                         PHD 1997 Duke University
    ## 3714                   PHD 1994 University of Toronto
    ## 3715              PHD 2005 Carnegie-Mellon University
    ## 3716       PHD 2000 Iowa State Univ of Sci &amp; Tech
    ## 3717                   PHD 2010 University of Florida
    ## 3718                                            PHD  
    ## 3719               BFA 1993 Univ of Wisconsin-Oshkosh
    ## 3720                     PHD 2016 Stanford University
    ## 3721           PHD 2014 Univ of Michigan at Ann Arbor
    ## 3722             PHD 2000 Univ of California Berkeley
    ## 3723             MSA 2015 Univ of Wisconsin-Milwaukee
    ## 3724                     PHD 2005 Stanford University
    ## 3725                                        DVM 2013 
    ## 3726           PHD 2012 Pennsylvania State University
    ## 3727                        EDD 2017 Edgewood College
    ## 3728       PHD 2008 SUNY Col Environ Sci &amp; Forest
    ## 3729               MSW 2006 Univ of Wisconsin-Madison
    ## 3730               PHD 2016 Univ of Wisconsin-Madison
    ## 3731           PHD 2000 Univ of Minnesota-Twin Cities
    ## 3732           PHD 2013 Univ of Minnesota-Twin Cities
    ## 3733             MS 2010 Univ of Wisconsin-Whitewater
    ## 3734             MS 1996 Univ of Wisconsin-Whitewater
    ## 3735                         PHD 2010 Yale University
    ## 3736                    PHD 1977 Princeton University
