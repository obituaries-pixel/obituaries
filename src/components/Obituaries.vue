<script setup>
const deadPeople = [
  {
    name: 'Jesus Christ',
    age: '33',
    achievement: 'Founded Christianity, considered the Son of God by many.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/4/4a/Christ_in_the_Wilderness_-_Ivan_Kramskoy_-_Google_Art_Project.jpg'
  },
  {
    name: 'Adolf Hitler',
    age: '56',
    achievement: 'Leader of Nazi Germany, initiated World War II and the Holocaust.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/d/dc/Adolf_Hitler_cropped_restored.jpg'
  },
  {
    name: 'Pope John Paul II',
    age: '84',
    achievement: 'One of the most influential leaders of the 20th century, helped end communist rule in Europe.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/3/36/JohannesPaul2-1.jpg'
  },
  {
    name: 'Jeffrey Epstein',
    age: '66',
    achievement: 'Wealthy financier and convicted sex offender with high-profile connections.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/e/e0/Jeffrey_Epstein_2017_official_photo.jpg'
  },
  {
    name: 'Pablo Escobar',
    age: '44',
    achievement: 'Infamous Colombian drug lord and narco-terrorist, leader of the Medellín Cartel.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/9/9a/Pablo_Escobar_Mugshot.jpg'
  },
  {
    name: 'Stephen Hawking',
    age: '76',
    achievement: 'Theoretical physicist known for his work on black holes and "A Brief History of Time".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/e/eb/Stephen_Hawking.StarChild.jpg'
  },
  {
    name: 'Albert Einstein',
    age: '76',
    achievement: 'Developed the theory of relativity, one of the two pillars of modern physics.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/3/3e/Einstein_1921_by_F_Schmutzer_-_restoration.jpg'
  },
  {
    name: 'Marilyn Monroe',
    age: '36',
    achievement: 'Iconic American actress, model, and singer; a major sex symbol of the 1950s.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/4/4e/Marilyn_Monroe_Publicity_Photo_for_The_Seven_Year_Itch.jpg'
  },
  {
    name: 'Leonardo da Vinci',
    age: '67',
    achievement: 'Renaissance polymath known for the Mona Lisa and The Last Supper.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/c/cb/Francesco_Melzi_-_Portrait_of_Leonardo.png'
  },
  {
    name: 'Mahatma Gandhi',
    age: '78',
    achievement: 'Leader of the Indian independence movement against British rule using nonviolent resistance.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/7/7a/Mahatma-Gandhi%2C_studio%2C_1931.jpg'
  },
  {
    name: 'Nelson Mandela',
    age: '95',
    achievement: 'South African anti-apartheid revolutionary and the country\'s first black president.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/0/02/Nelson_Mandela_1994.jpg'
  },
  {
    name: 'William Shakespeare',
    age: '52',
    achievement: 'Widely regarded as the greatest writer in the English language and the world\'s greatest dramatist.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/a2/Shakespeare.jpg'
  },
  {
    name: 'Martin Luther King Jr.',
    age: '39',
    achievement: 'Civil rights leader who advocated for racial equality through nonviolent protest.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/0/05/Martin_Luther_King%2C_Jr..jpg'
  },
  {
    name: 'Marie Curie',
    age: '66',
    achievement: 'Physicist and chemist who conducted pioneering research on radioactivity.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/c/c8/Marie_Curie_c1900.jpg'
  },
  {
    name: 'Abraham Lincoln',
    age: '56',
    achievement: '16th U.S. President who led the country through the Civil War and abolished slavery.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/1/1b/Abraham_Lincoln_November_1863.jpg'
  },
  {
    name: 'Princess Diana',
    age: '36',
    achievement: 'Member of the British royal family and global icon known for her charity work.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/5/5e/Diana%2C_Princess_of_Wales_1997_uncropped.jpg'
  },
  {
    name: 'Steve Jobs',
    age: '56',
    achievement: 'Co-founder of Apple Inc. and pioneer of the personal computer revolution.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/d/d9/Steve_Jobs_Headshot_2010-edit.jpg'
  },
  {
    name: 'Elvis Presley',
    age: '42',
    achievement: 'The "King of Rock and Roll," one of the most significant cultural icons of the 20th century.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/9/99/Elvis_Presley_promoting_Jailhouse_Rock.jpg'
  },
  {
    name: 'Michael Jackson',
    age: '50',
    achievement: 'The "King of Pop," one of the best-selling music artists of all time.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/3/31/Michael_Jackson_in_1984.jpg'
  },
  {
    name: 'Winston Churchill',
    age: '90',
    achievement: 'British Prime Minister who led the United Kingdom to victory in World War II.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/bc/Sir_Winston_Churchill_1941_Statesman.jpg'
  },
  {
    name: 'John F. Kennedy',
    age: '46',
    achievement: '35th U.S. President during the Cold War and Cuban Missile Crisis.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/c/c3/John_F._Kennedy%2C_White_House_color_photo_portrait.jpg'
  },
  {
    name: 'Mother Teresa',
    age: '87',
    achievement: 'Founded the Missionaries of Charity and dedicated her life to helping the poor.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/d/d6/Mother_Teresa_1.jpg'
  },
  {
    name: 'Isaac Newton',
    age: '84',
    achievement: 'Physicist and mathematician who formulated the laws of motion and universal gravitation.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/3/39/GodfreyKneller-IsaacNewton-1689.jpg'
  },
  {
    name: 'Vincent van Gogh',
    age: '37',
    achievement: 'Post-impressionist painter who created iconic works like "The Starry Night".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/4/4c/Vincent_van_Gogh_-_Self-Portrait_-_Google_Art_Project_%28454045%29.jpg'
  },
  {
    name: 'Wolfgang Amadeus Mozart',
    age: '35',
    achievement: 'Prolific and influential composer of the Classical era.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/1/1e/Wolfgang-amadeus-mozart_1.jpg'
  },
  {
    name: 'Charles Darwin',
    age: '73',
    achievement: 'Naturalist who proposed the theory of evolution by natural selection.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/2/2e/Charles_Darwin_seated_crop.jpg'
  },
  {
    name: 'Julius Caesar',
    age: '56',
    achievement: 'Roman general and statesman who played a critical role in the rise of the Roman Empire.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/6/62/Retrato_de_Julio_C%C3%A9sar_%2826724093101%29.jpg'
  },
  {
    name: 'Alexander the Great',
    age: '32',
    achievement: 'King of Macedon who created one of the largest empires in history.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/4/40/AlexanderTheGreat_Bust.jpg'
  },
  {
    name: 'George Washington',
    age: '67',
    achievement: 'First U.S. President and commander-in-chief of the Continental Army.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/b6/Gilbert_Stuart_Williamstown_Portrait_of_George_Washington.jpg'
  },
  {
    name: 'Napoléon Bonaparte',
    age: '51',
    achievement: 'French military leader and emperor who conquered much of Europe.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/5/50/Jacques-Louis_David_-_The_Emperor_Napoleon_in_His_Study_at_the_Tuileries_-_Google_Art_Project.jpg'
  },
  {
    name: 'Cleopatra',
    age: '39',
    achievement: 'The last active ruler of the Ptolemaic Kingdom of Egypt.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/3/3e/Cleopatra-VII-The-a-Altes-Museum-Berlin.jpg'
  },
  {
    name: 'Thomas Edison',
    age: '84',
    achievement: 'Inventor of the phonograph, the motion picture camera, and the light bulb.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/9/9d/Thomas_Edison2.jpg'
  },
  {
    name: 'Nikola Tesla',
    age: '86',
    achievement: 'Inventor and engineer known for his contributions to the design of the modern AC electricity system.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/7/79/Tesla_circa_1890.jpg'
  },
  {
    name: 'Amelia Earhart',
    age: '39',
    achievement: 'Aviation pioneer and the first female aviator to fly solo across the Atlantic Ocean.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/b4/Amelia_Earhart_1932.jpg'
  },
  {
    name: 'Rosa Parks',
    age: '92',
    achievement: 'Civil rights activist whose refusal to give up her bus seat sparked the Montgomery bus boycott.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/c/c4/Rosa_Parks_2.jpg'
  },
  {
    name: 'Freddie Mercury',
    age: '45',
    achievement: 'Lead singer of the rock band Queen, known for his powerful voice and stage presence.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/e/ef/Freddie_Mercury_performing_in_New_Haven%2C_CT%2C_November_1977.jpg'
  },
  {
    name: 'John Lennon',
    age: '40',
    achievement: 'Founder, co-songwriter, and co-lead vocalist of the Beatles.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/8/85/John_Lennon_1969_%28cropped%29.jpg'
  },
  {
    name: 'Bruce Lee',
    age: '32',
    achievement: 'Martial artist and actor who popularized martial arts films in the West.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/c/ca/Bruce_Lee_1973.jpg'
  },
  {
    name: 'Audrey Hepburn',
    age: '63',
    achievement: 'Film and fashion icon, and later a goodwill ambassador for UNICEF.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/5/5e/Audrey_Hepburn_1956.jpg'
  },
  {
    name: 'Walt Disney',
    age: '65',
    achievement: 'Pioneer of the American animation industry and creator of Disneyland.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/d/df/Walt_Disney_1946.JPG'
  },
  {
    name: 'Coco Chanel',
    age: '87',
    achievement: 'Fashion designer and founder of the Chanel brand.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/bc/Coco_Chanel_1920.jpg'
  },
  {
    name: 'Frida Kahlo',
    age: '47',
    achievement: 'Mexican painter known for her many portraits, self-portraits, and works inspired by nature.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/0/06/Frida_Kahlo%2C_by_Guillermo_Kahlo.jpg'
  },
  {
    name: 'Malcolm X',
    age: '39',
    achievement: 'Human rights activist and a prominent figure in the Nation of Islam.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/c/cb/Malcolm_X_NYWTS_2.jpg'
  },
  {
    name: 'Franklin D. Roosevelt',
    age: '63',
    achievement: '32nd U.S. President who led the country through the Great Depression and World War II.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/4/42/FDR_1944_Color_Portrait.jpg'
  },
  {
    name: 'Che Guevara',
    age: '39',
    achievement: 'Marxist revolutionary and a major figure of the Cuban Revolution.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/5/58/CheHigh.jpg'
  },
  {
    name: 'Joan of Arc',
    age: '19',
    achievement: 'Heroine of France for her role during the Lancastrian phase of the Hundred Years\' War.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/3/39/Joan_of_arc_miniature_graded.jpg'
  },
  {
    name: 'Christopher Columbus',
    age: '54',
    achievement: 'Explorer whose voyages across the Atlantic Ocean opened the way for European exploration.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/3/30/Ridolfo_Ghirlandaio_-_Portrait_of_Christopher_Columbus.jpg'
  },
  {
    name: 'Marco Polo',
    age: '69',
    achievement: 'Venetian merchant and explorer who traveled through Asia and chronicled his experiences.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/e/ee/Marco_Polo_portrait.jpg'
  },
  {
    name: 'Genghis Khan',
    age: '65',
    achievement: 'Founder and first Great Khan of the Mongol Empire.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/3/35/Yuan_Emperor_Genghis_Khan.jpg'
  },
  {
    name: 'Socrates',
    age: '71',
    achievement: 'Classical Greek philosopher credited as one of the founders of Western philosophy.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/a4/Socrates_Louvre.jpg'
  },
  {
    name: 'Plato',
    age: '80',
    achievement: 'Philosopher and founder of the Academy in Athens.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/8/88/Plato_Silanion_Musei_Capitolini_MC1377.jpg'
  },
  {
    name: 'Aristotle',
    age: '62',
    achievement: 'Greek philosopher and polymath during the Classical period in Ancient Greece.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/ae/Aristotle_Altemps_Inv8575.jpg'
  },
  {
    name: 'Galileo Galilei',
    age: '77',
    achievement: 'Astronomer and physicist who championed heliocentrism and the scientific method.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/d/d4/Justus_Sustermans_-_Portrait_of_Galileo_Galilei%2C_1636.jpg'
  },
  {
    name: 'Sigmund Freud',
    age: '83',
    achievement: 'Neurologist and the founder of psychoanalysis.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/1/12/Sigmund_Freud_LIFE.jpg'
  },
  {
    name: 'Charles Chaplin',
    age: '88',
    achievement: 'Comic actor and filmmaker who rose to fame during the era of silent film.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/3/34/Charlie_Chaplin_portrait.jpg'
  },
  {
    name: 'Bob Marley',
    age: '36',
    achievement: 'Reggae singer and songwriter who became a global symbol of Jamaican culture.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/5/5e/Bob-Marley.jpg'
  },
  {
    name: 'Whitney Houston',
    age: '48',
    achievement: 'One of the best-selling music artists of all time, known for her powerful vocals.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/0/05/Whitney_Houston_1991.jpg'
  },
  {
    name: 'Amy Winehouse',
    age: '27',
    achievement: 'Singer and songwriter known for her deep, expressive vocals and eclectic mix of genres.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/2/22/Amy_Winehouse_f_cropped.jpg'
  },
  {
    name: 'Kurt Cobain',
    age: '27',
    achievement: 'Lead singer and guitarist of the rock band Nirvana, a key figure of the grunge movement.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/c/c0/Kurt_Cobain_1992.jpg'
  },
  {
    name: 'James Dean',
    age: '24',
    achievement: 'Cultural icon of teenage disillusionment and social estrangement.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/4/41/James_Dean_in_Rebel_Without_a_Cause_portrait.jpg'
  },
  {
    name: 'Heath Ledger',
    age: '28',
    achievement: 'Actor known for his roles in "Brokeback Mountain" and "The Dark Knight".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/af/Heath_Ledger_%28Berlin_Film_Festival_2006%29.jpg'
  },
  {
    name: 'David Bowie',
    age: '69',
    achievement: 'Singer-songwriter and actor, a leading figure in the music industry for over five decades.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/e/e8/David-Bowie_The_Stars_are_out_Tonight_Shot_by_Floria_Sigismondi_2013.jpg'
  },
  {
    name: 'Prince',
    age: '57',
    achievement: 'Musician and multi-instrumentalist known for his eclectic work and flamboyant stage presence.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/d/d7/Prince_at_Coachella_001.jpg'
  },
  {
    name: 'Robin Williams',
    age: '63',
    achievement: 'Actor and comedian known for his improvisational skills and diverse range of roles.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/5/59/Robin_Williams_2011a_%28cropped%29.jpg'
  },
  {
    name: 'Muhammad Ali',
    age: '74',
    achievement: 'Professional boxer and activist, widely regarded as one of the greatest athletes of all time.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/8/89/Muhammad_Ali_NYWTS.jpg'
  },
  {
    name: 'Kobe Bryant',
    age: '41',
    achievement: 'NBA basketball player who spent his entire 20-year career with the Los Angeles Lakers.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/5/51/Kobe_Bryant_2014.jpg'
  },
  {
    name: 'Neil Armstrong',
    age: '82',
    achievement: 'Astronaut and aeronautical engineer who was the first person to walk on the Moon.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/0/0d/Neil_Armstrong_pose.jpg'
  },
  {
    name: 'Buzz Aldrin',
    age: '94 (Still Alive)',
    achievement: 'Astronaut and the second person to walk on the Moon. (Note: Included for context, but technically still alive)',
    image: 'https://upload.wikimedia.org/wikipedia/commons/d/dc/Buzz_Aldrin.jpg'
  },
  {
    name: 'Alan Turing',
    age: '41',
    achievement: 'Mathematician and computer scientist who cracked the Enigma code and pioneered AI.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/1/17/Alan_Turing_Aged_16.jpg'
  },
  {
    name: 'Grace Hopper',
    age: '85',
    achievement: 'Computer scientist and U.S. Navy rear admiral who pioneered COBOL.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/ad/Commodore_Grace_M._Hopper%2C_USN_%28uncovered%29.jpg'
  },
  {
    name: 'Steve Irwin',
    age: '44',
    achievement: 'Australian zookeeper and conservationist, known as "The Crocodile Hunter".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/2/2e/Steve_Irwin.jpg'
  },
  {
    name: 'George Orwell',
    age: '46',
    achievement: 'Writer and journalist known for "Animal Farm" and "Nineteen Eighty-Four".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/7/7e/George_Orwell_press_photo.jpg'
  },
  {
    name: 'Ernest Hemingway',
    age: '61',
    achievement: 'Novelist and short-story writer known for his economical and understated style.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/2/28/ErnestHemingway.jpg'
  },
  {
    name: 'Mark Twain',
    age: '74',
    achievement: 'Writer and humorist known for "The Adventures of Tom Sawyer" and "Huckleberry Finn".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/0/0c/Mark_Twain_by_AF_Bradley.jpg'
  },
  {
    name: 'Oscar Wilde',
    age: '46',
    achievement: 'Irish poet and playwright known for "The Picture of Dorian Gray".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/9/92/Oscar_Wilde_3.jpg'
  },
  {
    name: 'Virginia Woolf',
    age: '59',
    achievement: 'Modernist writer known for her stream of consciousness technique.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/0/0b/Virginia_Woolf_1927.jpg'
  },
  {
    name: 'Jane Austen',
    age: '41',
    achievement: 'Novelist known for her social commentary and irony in works like "Pride and Prejudice".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/c/cc/CassandraAusten-JaneAusten%28c.1810%29_colored.jpg'
  },
  {
    name: 'Emily Dickinson',
    age: '55',
    achievement: 'Poet known for her unique use of form and syntax.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/5/5d/Emily_Dickinson_daguerreotype.jpg'
  },
  {
    name: 'Edgar Allan Poe',
    age: '40',
    achievement: 'Writer and poet known for his tales of mystery and the macabre.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/9/97/Edgar_Allan_Poe%2C_circa_1849%2C_restored%2C_digital_colorized.jpg'
  },
  {
    name: 'F. Scott Fitzgerald',
    age: '44',
    achievement: 'Novelist whose works illustrate the Jazz Age, including "The Great Gatsby".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/5/5c/F_Scott_Fitzgerald_1921.jpg'
  },
  {
    name: 'J.R.R. Tolkien',
    age: '81',
    achievement: 'Author of "The Hobbit" and "The Lord of the Rings".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/b4/Tolkien_1916.jpg'
  },
  {
    name: 'C.S. Lewis',
    age: '64',
    achievement: 'Author of "The Chronicles of Narnia" and Christian apologist.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/2/29/C.s.lewis3.jpg'
  },
  {
    name: 'Roald Dahl',
    age: '74',
    achievement: 'Children\'s author known for "Charlie and the Chocolate Factory".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/ba/Roald_Dahl_6_20_May_1954.jpg'
  },
  {
    name: 'Maya Angelou',
    age: '86',
    achievement: 'Poet and civil rights activist known for "I Know Why the Caged Bird Sings".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/b7/Maya_Angelou_at_Clinton_inauguration.jpg'
  },
  {
    name: 'Tupac Shakur',
    age: '25',
    achievement: 'Highly influential rapper and actor, a symbol of resistance and activism.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/b5/Tupac_Shakur_222.jpg'
  },
  {
    name: 'The Notorious B.I.G.',
    age: '24',
    achievement: 'Central figure in the East Coast hip hop scene.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/b9/The_Notorious_B.I.G._1994.jpg'
  },
  {
    name: 'Jim Morrison',
    age: '27',
    achievement: 'Lead singer of the rock band The Doors.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/1/1a/Jim_Morrison_1969.jpg'
  },
  {
    name: 'Jimi Hendrix',
    age: '27',
    achievement: 'Widely regarded as one of the most influential electric guitarists in history.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/ae/Jimi_Hendrix_1967.png'
  },
  {
    name: 'Janis Joplin',
    age: '27',
    achievement: 'Powerful blues-rock singer and a symbol of the 1960s counterculture.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/9/94/Janis_Joplin_1970.jpg'
  },
  {
    name: 'Sid Vicious',
    age: '21',
    achievement: 'Bassist of the punk rock band the Sex Pistols.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/d/de/Sid_Vicious.jpg'
  },
  {
    name: 'Lou Reed',
    age: '71',
    achievement: 'Musician and songwriter, co-founder of the Velvet Underground.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/0/01/Lou_Reed_1977.jpg'
  },
  {
    name: 'Leonard Cohen',
    age: '82',
    achievement: 'Singer-songwriter and poet known for "Hallelujah".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/d/de/Leonard_Cohen_2187.jpg'
  },
  {
    name: 'George Harrison',
    age: '58',
    achievement: 'Lead guitarist of the Beatles.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/4/42/George_Harrison_1974.jpg'
  },
  {
    name: 'Carrie Fisher',
    age: '60',
    achievement: 'Actress best known for playing Princess Leia in the Star Wars films.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/d/d1/Carrie_Fisher_2013.jpg'
  },
  {
    name: 'Alan Rickman',
    age: '69',
    achievement: 'Actor known for his roles in "Die Hard" and the Harry Potter series.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/b2/Alan_Rickman_2011.jpg'
  },
  {
    name: 'Patrick Swayze',
    age: '57',
    achievement: 'Actor known for "Dirty Dancing" and "Ghost".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/b4/Patrick_Swayze_1989.jpg'
  },
  {
    name: 'Paul Walker',
    age: '40',
    achievement: 'Actor best known for his role in the Fast & Furious franchise.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/a2/Paul_Walker_2009.jpg'
  },
  {
    name: 'River Phoenix',
    age: '23',
    achievement: 'Actor and musician known for "Stand by Me" and "My Own Private Idaho".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/bc/River_Phoenix_1989.jpg'
  },
  {
    name: 'Stan Lee',
    age: '95',
    achievement: 'Comic book writer and editor who co-created many Marvel characters.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/7/7b/Stan_Lee_by_Gage_Skidmore_3.jpg'
  },
  {
    name: 'Aretha Franklin',
    age: '76',
    achievement: 'The "Queen of Soul", one of the most honored artists in Grammy history.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/c/c6/Aretha_Franklin_1968.jpg'
  },
  {
    name: 'James Brown',
    age: '73',
    achievement: 'The "Godfather of Soul", a progenitor of funk music.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/1/1e/James_Brown_1973.jpg'
  },
  {
    name: 'Ray Charles',
    age: '73',
    achievement: 'Pioneered soul music by combining blues, rhythm and blues, and gospel.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/af/Ray_Charles_1969.jpg'
  },
  {
    name: 'Johnny Cash',
    age: '71',
    achievement: 'One of the best-selling music artists of all time, known for his deep voice and country music.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/1/1d/Johnny_Cash_1969.jpg'
  },
  {
    name: 'Frank Sinatra',
    age: '82',
    achievement: 'One of the most popular and influential musical artists of the 20th century.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/af/Frank_Sinatra_%27The_Frank_Sinatra_Show%27_1957.JPG'
  },
  {
    name: 'Ella Fitzgerald',
    age: '79',
    achievement: 'The "First Lady of Song", known for her purity of tone and impeccable diction.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/a1/Ella_Fitzgerald_%28Gottlieb_02871%29.jpg'
  },
  {
    name: 'Billie Holiday',
    age: '44',
    achievement: 'Jazz singer with a unique phrasing and influence on jazz and pop singing.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/0/00/Billie_Holiday_1947_%28Gottlieb_04251%29.jpg'
  },
  {
    name: 'Miles Davis',
    age: '65',
    achievement: 'Trumpeter and composer, among the most influential figures in jazz history.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/f/fa/Miles_Davis_by_Gottlieb_1947.jpg'
  },
  {
    name: 'Louis Armstrong',
    age: '69',
    achievement: 'Trumpeter and vocalist, among the most influential figures in jazz.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/0/0e/Louis_Armstrong_restored.jpg'
  },
  {
    name: 'Duke Ellington',
    age: '75',
    achievement: 'Composer, pianist, and leader of a jazz orchestra for over fifty years.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/af/Duke_Ellington_-_Gottlieb_1946.jpg'
  },
  {
    name: 'Edith Piaf',
    age: '47',
    achievement: 'France\'s national chanteuse and one of the country\'s greatest international stars.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/bd/Edith_Piaf_World_Telegram.jpg'
  },
  {
    name: 'Luciano Pavarotti',
    age: '71',
    achievement: 'Operatic tenor who became one of the most commercially successful tenors of all time.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/c/c6/Luciano_Pavarotti_1992.jpg'
  },
  {
    name: 'George Michael',
    age: '53',
    achievement: 'Singer-songwriter and one of the best-selling music artists of all time.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/e/ee/George_Michael_Faith_Tour_1988.jpg'
  },
  {
    name: 'Donna Summer',
    age: '63',
    achievement: 'The "Queen of Disco", prominent during the disco era of the late 1970s.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/e/ea/Donna_Summer_1977.jpg'
  },
  {
    name: 'Etta James',
    age: '73',
    achievement: 'Singer who performed in various genres, including blues, R&B, soul, rock and roll, jazz and gospel.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/8/87/Etta_James_1962.jpg'
  },
  {
    name: 'B.B. King',
    age: '89',
    achievement: 'The "King of the Blues", one of the most influential blues guitarists of all time.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/e/ea/B.B._King_1990.jpg'
  },
  {
    name: 'Prince Rogers Nelson',
    age: '57',
    achievement: 'Legendary musician known for his wide vocal range and flamboyant stage presence.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/d/d7/Prince_at_Coachella_001.jpg'
  },
  {
    name: 'George Carlin',
    age: '71',
    achievement: 'Stand-up comedian, social critic, and author known for his "Seven Dirty Words" routine.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/c/cd/Carlin_by_Gage_Skidmore.jpg'
  },
  {
    name: 'Joan Rivers',
    age: '81',
    achievement: 'Comedian, actress, and writer known for her controversial persona and sharp wit.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/a2/Joan_Rivers_2010.jpg'
  },
  {
    name: 'Richard Pryor',
    age: '65',
    achievement: 'Comedian and actor known for his uncompromising examinations of racism and topical issues.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/3/3a/Richard_Pryor_1986.jpg'
  },
  {
    name: 'Gene Wilder',
    age: '83',
    achievement: 'Actor known for his roles in "Willy Wonka & the Chocolate Factory" and "Young Frankenstein".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/1/1b/Gene_Wilder_1970.JPG'
  },
  {
    name: 'Burt Reynolds',
    age: '82',
    achievement: 'Actor and sex symbol, a top box-office draw for several consecutive years.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/0/08/Burt_Reynolds_1972.jpg'
  },
  {
    name: 'Roger Moore',
    age: '89',
    achievement: 'Actor best known for playing James Bond in seven feature films.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/f/fe/Roger_Moore_1973.jpg'
  },
  {
    name: 'Christopher Lee',
    age: '93',
    achievement: 'Actor known for his roles in horror films, "Lord of the Rings", and "Star Wars".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/f/fc/Sir_Christopher_Lee_at_the_Berlin_Film_Festival_2013.jpg'
  },
  {
    name: 'Sean Connery',
    age: '90',
    achievement: 'The first actor to portray James Bond on film.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/8/8e/Sean_Connery_1980.jpg'
  },
  {
    name: 'Kirk Douglas',
    age: '103',
    achievement: 'Actor and filmmaker, a major star of the Hollywood Golden Age.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/ab/Kirk_Douglas_1955.jpg'
  },
  {
    name: 'Olivia de Havilland',
    age: '104',
    achievement: 'Actress, one of the last surviving stars from the Golden Age of Hollywood cinema.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/ae/Olivia_de_Havilland_1940s.jpg'
  },
  {
    name: 'Lauren Bacall',
    age: '89',
    achievement: 'Actress known for her distinctive voice and sultry looks.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/e/ec/Lauren_Bacall_1945.jpg'
  },
  {
    name: 'Humphrey Bogart',
    age: '57',
    achievement: 'Actor, cultural icon of the 1940s and 1950s.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/b3/Humphrey_Bogart_1940.jpg'
  },
  {
    name: 'Katherine Hepburn',
    age: '96',
    achievement: 'Leading lady in Hollywood for more than 60 years.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/0/08/Katharine_Hepburn_promo_pic.jpg'
  },
  {
    name: 'Grace Kelly',
    age: '52',
    achievement: 'Actress who became Princess of Monaco.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/a7/Grace_Kelly_1950s.jpg'
  },
  {
    name: 'Marlon Brando',
    age: '80',
    achievement: 'Considered one of the most influential actors in 20th-century cinema.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/5/53/Marlon_Brando_publicity_for_One-Eyed_Jacks.png'
  },
  {
    name: 'Gregory Peck',
    age: '87',
    achievement: 'One of the most popular film stars from the 1940s to the 1960s.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/4/4e/Gregory_Peck_1948.jpg'
  },
  {
    name: 'Cary Grant',
    age: '82',
    achievement: 'One of classic Hollywood\'s definitive leading men.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/3/32/Cary_Grant_1941.jpg'
  },
  {
    name: 'Elizabeth Taylor',
    age: '79',
    achievement: 'Actress, businesswoman, and humanitarian.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/3/30/Elizabeth_Taylor_1953.jpg'
  },
  {
    name: 'Richard Burton',
    age: '58',
    achievement: 'Welsh actor known for his mellifluous baritone voice.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/f/ff/Richard_Burton_1960.jpg'
  },
  {
    name: 'Ingrid Bergman',
    age: '67',
    achievement: 'Swedish actress who won three Academy Awards.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/af/Ingrid_Bergman_at_the_1945_Academy_Awards.jpg'
  },
  {
    name: 'John Wayne',
    age: '72',
    achievement: 'Actor who became an enduring American icon through his roles in Westerns.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/3/3d/John_Wayne_1960.jpg'
  },
  {
    name: 'Steve McQueen',
    age: '50',
    achievement: 'Actor nicknamed "The King of Cool".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/f/f6/Steve_McQueen_1960s.jpg'
  },
  {
    name: 'Robin Williams',
    age: '63',
    achievement: 'Beloved actor and comedian known for his incredible range.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/5/59/Robin_Williams_2011a_%28cropped%29.jpg'
  },
  {
    name: 'Philip Seymour Hoffman',
    age: '46',
    achievement: 'Highly acclaimed actor known for his intense and versatile performances.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/1/1b/Philip_Seymour_Hoffman_2011.jpg'
  },
  {
    name: 'James Gandolfini',
    age: '51',
    achievement: 'Actor best known for his role as Tony Soprano in "The Sopranos".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/4/4b/James_Gandolfini_2010.jpg'
  },
  {
    name: 'Brittany Murphy',
    age: '32',
    achievement: 'Actress known for "Clueless" and "8 Mile".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/6/6f/Brittany_Murphy_2001.jpg'
  },
  {
    name: 'Corey Haim',
    age: '38',
    achievement: 'Teen idol of the 1980s, known for "The Lost Boys".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/3/36/Corey_Haim_2009.jpg'
  },
  {
    name: 'Gary Coleman',
    age: '42',
    achievement: 'Child actor best known for his role in the sitcom "Diff\'rent Strokes".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/1/15/Gary_Coleman_2008.jpg'
  },
  {
    name: 'Farrah Fawcett',
    age: '62',
    achievement: 'Actress and sex symbol, best known for "Charlie\'s Angels".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/bd/Farrah_Fawcett_1977.jpg'
  },
  {
    name: 'Michael Clarke Duncan',
    age: '54',
    achievement: 'Actor known for his breakout role in "The Green Mile".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/0/00/Michael_Clarke_Duncan_2009.jpg'
  },
  {
    name: 'Patrick McGoohan',
    age: '80',
    achievement: 'Actor, creator and star of the cult television series "The Prisoner".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/7/7b/Patrick_McGoohan_1967.jpg'
  },
  {
    name: 'Paul Newman',
    age: '83',
    achievement: 'Actor, film director, race car driver, and philanthropist.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/d/d3/Paul_Newman_1960.jpg'
  },
  {
    name: 'Charlton Heston',
    age: '84',
    achievement: 'Actor known for heroic roles in "The Ten Commandments" and "Ben-Hur".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/b3/Charlton_Heston_1960.jpg'
  },
  {
    name: 'Heath Ledger',
    age: '28',
    achievement: 'Actor known for his unforgettable portrayal of the Joker.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/af/Heath_Ledger_%28Berlin_Film_Festival_2006%29.jpg'
  },
  {
    name: 'Bernie Mac',
    age: '50',
    achievement: 'Comedian and actor known for "The Bernie Mac Show".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/c/c5/Bernie_Mac_at_the_premiere_of_Ocean%27s_Thirteen.jpg'
  },
  {
    name: 'Isaac Hayes',
    age: '65',
    achievement: 'Musician and actor known for the "Theme from Shaft" and voicing Chef on "South Park".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/d/d2/Isaac_Hayes_at_the_2007_Wondercon_1.jpg'
  },
  {
    name: 'Alexander McQueen',
    age: '40',
    achievement: 'Renowned fashion designer and couturier.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/3/30/Alexander_McQueen_2009.jpg'
  },
  {
    name: 'Steve Jobs',
    age: '56',
    achievement: 'Co-founder of Apple and visionary of the digital age.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/d/d9/Steve_Jobs_Headshot_2010-edit.jpg'
  },
  {
    name: 'Neil Armstrong',
    age: '82',
    achievement: 'The first person to set foot on the Moon.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/0/0d/Neil_Armstrong_pose.jpg'
  },
  {
    name: 'Sally Ride',
    age: '61',
    achievement: 'The first American woman in space.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/3/3a/Sally_Ride_1984.jpg'
  },
  {
    name: 'Chadwick Boseman',
    age: '43',
    achievement: 'Actor best known for his role as Black Panther in the MCU.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/2/23/Chadwick_Boseman_by_Gage_Skidmore.jpg'
  },
  {
    name: 'Naya Rivera',
    age: '33',
    achievement: 'Actress and singer known for her role in "Glee".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/1/1a/Naya_Rivera_2011.jpg'
  },
  {
    name: 'Anthony Bourdain',
    age: '61',
    achievement: 'Chef, author, and travel documentarian.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/f/ff/Anthony_Bourdain_2014.jpg'
  },
  {
    name: 'Kate Spade',
    age: '55',
    achievement: 'Fashion designer and founder of the designer brand Kate Spade New York.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/af/Kate_Spade_2008.jpg'
  },
  {
    name: 'Avicii',
    age: '28',
    achievement: 'Swedish DJ and music producer who pioneered electronic dance music.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/1/10/Avicii_in_2014.jpg'
  },
  {
    name: 'Mac Miller',
    age: '26',
    achievement: 'Rapper and singer-songwriter known for his introspection and evolution.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/5/5a/Mac_Miller_2017.jpg'
  },
  {
    name: 'Juice WRLD',
    age: '21',
    achievement: 'Rapper and singer who was a leading figure in the emo rap genre.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/c/c5/Juice_WRLD_2018.jpg'
  },
  {
    name: 'XXXTentacion',
    age: '20',
    achievement: 'Rapper known for his raw and emotionally charged music.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/e/ef/XXXTentacion_%28cropped%29.jpg'
  },
  {
    name: 'Bill Withers',
    age: '81',
    achievement: 'Singer-songwriter known for "Lean on Me" and "Ain\'t No Sunshine".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/5/52/Bill_Withers_1976.jpg'
  },
  {
    name: 'Little Richard',
    age: '87',
    achievement: 'Influential figure in popular music and culture for seven decades.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/1/1b/Little_Richard_1966.jpg'
  },
  {
    name: 'Ennio Morricone',
    age: '91',
    achievement: 'Composer who wrote scores for more than 400 films and television series.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/3/30/Ennio_Morricone_2007.jpg'
  },
  {
    name: 'Eddie Van Halen',
    age: '65',
    achievement: 'Musician and songwriter, main songwriter and lead guitarist of Van Halen.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/bd/Eddie_Van_Halen_1993.jpg'
  },
  {
    name: 'Alex Trebek',
    age: '80',
    achievement: 'Longtime host of the game show "Jeopardy!".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/7/77/Alex_Trebek_2012.jpg'
  },
  {
    name: 'Larry King',
    age: '87',
    achievement: 'Television host and radio personality who conducted over 30,000 interviews.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/2/22/Larry_King_2010.jpg'
  },
  {
    name: 'Christopher Plummer',
    age: '91',
    achievement: 'Actor whose career spanned seven decades, known for "The Sound of Music".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/8/80/Christopher_Plummer_2014.jpg'
  },
  {
    name: 'Prince Philip',
    age: '99',
    achievement: 'Husband of Queen Elizabeth II and the longest-serving royal consort in British history.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/d/de/Prince_Philip%2C_Duke_of_Edinburgh_2013.jpg'
  },
  {
    name: 'Desmond Tutu',
    age: '90',
    achievement: 'South African Anglican bishop and anti-apartheid and human rights activist.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/1/1a/Desmond_Tutu_2012.jpg'
  },
  {
    name: 'Sidney Poitier',
    age: '94',
    achievement: 'The first Black actor to win the Academy Award for Best Actor.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/ba/Sidney_Poitier_1968.jpg'
  },
  {
    name: 'Betty White',
    age: '99',
    achievement: 'Actress and comedian with the longest television career of any entertainer.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/a2/Betty_White_2009.jpg'
  },
  {
    name: 'Mikhail Gorbachev',
    age: '91',
    achievement: 'The last leader of the Soviet Union, known for his policies of glasnost and perestroika.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/0/01/Mikhail_Gorbachev_1987.jpg'
  },
  {
    name: 'Queen Elizabeth II',
    age: '96',
    achievement: 'Queen of the United Kingdom and other Commonwealth realms for over 70 years.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/3/30/Queen_Elizabeth_II_in_March_2015.jpg'
  },
  {
    name: 'James Caan',
    age: '82',
    achievement: 'Actor known for his breakout role as Sonny Corleone in "The Godfather".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/5/53/James_Caan_1972.jpg'
  },
  {
    name: 'Olivia Newton-John',
    age: '73',
    achievement: 'Singer and actress best known for her role in the film "Grease".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/e/e0/Olivia_Newton-John_1970s.jpg'
  },
  {
    name: 'Coolio',
    age: '59',
    achievement: 'Rapper known for his 1995 hit single "Gangsta\'s Paradise".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/e/ec/Coolio_2014.jpg'
  },
  {
    name: 'Angela Lansbury',
    age: '96',
    achievement: 'Actress whose career spanned eight decades, known for "Murder, She Wrote".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/1/1a/Angela_Lansbury_1950.jpg'
  },
  {
    name: 'Robbie Coltrane',
    age: '72',
    achievement: 'Actor known for playing Rubeus Hagrid in the Harry Potter film series.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/b5/Robbie_Coltrane_2007.jpg'
  },
  {
    name: 'Takeoff',
    age: '28',
    achievement: 'Rapper best known as a member of the hip hop trio Migos.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/be/Takeoff_Migos_2017.jpg'
  },
  {
    name: 'Aaron Carter',
    age: '34',
    achievement: 'Singer and teen idol in the late 1990s and early 2000s.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/c/c5/Aaron_Carter_2018.jpg'
  },
  {
    name: 'Kevin Conroy',
    age: '66',
    achievement: 'Actor known for voicing the DC Comics character Batman in various media.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/0/07/Kevin_Conroy_by_Gage_Skidmore.jpg'
  },
  {
    name: 'Kirstie Alley',
    age: '71',
    achievement: 'Actress known for her role as Rebecca Howe on the sitcom "Cheers".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/f/ff/Kirstie_Alley_1994.jpg'
  },
  {
    name: 'Stephen "tWitch" Boss',
    age: '40',
    achievement: 'Freestyle hip hop dancer, choreographer, and actor.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/1/17/Stephen_tWitch_Boss_2013.jpg'
  },
  {
    name: 'Vivienne Westwood',
    age: '81',
    achievement: 'Fashion designer who brought modern punk and new wave fashions into the mainstream.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/0/02/Vivienne_Westwood_2010.jpg'
  },
  {
    name: 'Pele',
    age: '82',
    achievement: 'Brazilian professional footballer, widely regarded as one of the greatest players of all time.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/5/5e/Pele_con_la_copa_del_mundo.jpg'
  },
  {
    name: 'Pope Benedict XVI',
    age: '95',
    achievement: 'Head of the Catholic Church from 2005 until his resignation in 2013.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/d/de/Pope_Benedict_XVI_2010.jpg'
  },
  {
    name: 'Lisa Marie Presley',
    age: '54',
    achievement: 'Singer-songwriter and the only child of Elvis and Priscilla Presley.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/9/91/Lisa_Marie_Presley_2013.jpg'
  },
  {
    name: 'Jeff Beck',
    age: '78',
    achievement: 'Rock guitarist who played with the Yardbirds and led the Jeff Beck Group.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/1/1a/Jeff_Beck_2012.jpg'
  },
  {
    name: 'Gina Lollobrigida',
    age: '95',
    achievement: 'Italian actress, photojournalist, and politician.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/b3/Gina_Lollobrigida_1960.jpg'
  },
  {
    name: 'David Crosby',
    age: '81',
    achievement: 'Singer-songwriter and founding member of the Byrds and Crosby, Stills & Nash.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/5/52/David_Crosby_1976.jpg'
  },
  {
    name: 'Paco Rabanne',
    age: '88',
    achievement: 'Spanish fashion designer of Basque origin who became known as an enfant terrible.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/7/7b/Paco_Rabanne_1999.jpg'
  },
  {
    name: 'Burt Bacharach',
    age: '94',
    achievement: 'Composer, songwriter, record producer, and pianist who composed hundreds of pop hits.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/7/7a/Burt_Bacharach_1972.jpg'
  },
  {
    name: 'Raquel Welch',
    age: '82',
    achievement: 'Actress and singer who became an icon of the 1960s and 1970s.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/6/6f/Raquel_Welch_1968.jpg'
  },
  {
    name: 'Richard Belzer',
    age: '78',
    achievement: 'Stand-up comedian and actor best known for his role as John Munch.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/4/4e/Richard_Belzer_2011.jpg'
  },
  {
    name: 'Tom Sizemore',
    age: '61',
    achievement: 'Actor known for his supporting roles in "Saving Private Ryan" and "Black Hawk Down".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/1/15/Tom_Sizemore_2011.jpg'
  },
  {
    name: 'Lance Reddick',
    age: '60',
    achievement: 'Actor known for his roles in "The Wire" and the "John Wick" franchise.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/4/4d/Lance_Reddick_by_Gage_Skidmore.jpg'
  },
  {
    name: 'Harry Belafonte',
    age: '96',
    achievement: 'Singer, actor, and civil rights activist.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/b3/Harry_Belafonte_1954.jpg'
  },
  {
    name: 'Jerry Springer',
    age: '79',
    achievement: 'Broadcaster and politician best known for hosting "The Jerry Springer Show".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/2/23/Jerry_Springer_2011.jpg'
  },
  {
    name: 'Tina Turner',
    age: '83',
    achievement: 'The "Queen of Rock \'n\' Roll", known for her energetic stage presence.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/ba/Tina_Turner_1971.jpg'
  },
  {
    name: 'Tony Bennett',
    age: '96',
    achievement: 'Singer of traditional pop standards, big band, show tunes, and jazz.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/1/1b/Tony_Bennett_1960.jpg'
  },
  {
    name: 'Sinead O\'Connor',
    age: '56',
    achievement: 'Singer-songwriter who rose to fame with "Nothing Compares 2 U".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/1/1a/Sinead_O%27Connor_2011.jpg'
  },
  {
    name: 'Angus Cloud',
    age: '25',
    achievement: 'Actor known for his role as Fezco in the HBO series "Euphoria".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/a2/Angus_Cloud_2022.jpg'
  },
  {
    name: 'Jimmy Buffett',
    age: '76',
    achievement: 'Singer-songwriter and businessman known for "Margaritaville".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/d/de/Jimmy_Buffett_2010.jpg'
  },
  {
    name: 'Michael Gambon',
    age: '82',
    achievement: 'Actor who played Albus Dumbledore in the Harry Potter film series.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/1/10/Michael_Gambon_2007.jpg'
  },
  {
    name: 'Matthew Perry',
    age: '54',
    achievement: 'Actor best known for his role as Chandler Bing on the sitcom "Friends".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/b2/Matthew_Perry_2013.jpg'
  },
  {
    name: 'Andre Braugher',
    age: '61',
    achievement: 'Actor known for his roles in "Homicide: Life on the Street" and "Brooklyn Nine-Nine".',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/bc/Andre_Braugher_by_Gage_Skidmore.jpg'
  }
]
</script>

<template>
  <div class="obituaries">
    <h1>In Memoriam</h1>
    <p class="subtitle">A sad page about those who have left us.</p>
    
    <div class="grid">
      <div v-for="person in deadPeople" :key="person.name" class="card">
        <img :src="person.image" :alt="person.name" class="portrait" />
        <div class="info">
          <h2>{{ person.name }}</h2>
          <p><strong>Age:</strong> {{ person.age }}</p>
          <p><strong>Biggest Achievement:</strong> {{ person.achievement }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.obituaries {
  padding: 2rem;
  color: #ccc;
  background: #1a1a1a;
  min-height: 100vh;
  font-family: serif;
}

h1 {
  text-align: center;
  font-size: 3rem;
  margin-bottom: 0.5rem;
}

.subtitle {
  text-align: center;
  font-style: italic;
  margin-bottom: 3rem;
}

.grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
  gap: 1.5rem;
}

.card {
  background: #2a2a2a;
  border: 1px solid #444;
  padding: 1rem;
  text-align: center;
  border-radius: 8px;
  transition: transform 0.3s, box-shadow 0.3s;
  display: flex;
  flex-direction: column;
}

.card:hover {
  transform: translateY(-5px);
  border-color: #888;
  box-shadow: 0 10px 20px rgba(0,0,0,0.5);
}

.portrait {
  width: 100%;
  height: 350px;
  object-fit: cover;
  border-radius: 4px;
  filter: grayscale(100%);
  margin-bottom: 1rem;
  background: #333; /* Placeholder for loading */
}

.info {
  flex-grow: 1;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

h2 {
  margin: 0.5rem 0;
  color: #fff;
}

p {
  margin: 0.5rem 0;
}
</style>
