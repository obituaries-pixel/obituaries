
<script setup>
const deadPeople = [
  {
    name: 'Jesus Christ',
    age: '33',
    achievement: 'Founded Christianity, considered the Son of God by many.',
    causeOfDeath: 'Crucifixion by the Romans. Sadly, they died. Rest in pieces! ⚰️ So sad 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/4/4a/Christ_in_the_Wilderness_-_Ivan_Kramskoy_-_Google_Art_Project.jpg'
  },
  {
    name: 'Joseph Stalin',
    age: '74',
    achievement: 'Leader of the Soviet Union, industrialized the USSR but at the cost of millions of lives.',
    causeOfDeath: 'Cerebral hemorrhage after years of paranoia. Eaten by very hungry rats! 🐀 Rest in pieces! ⚰️',
    image: 'https://upload.wikimedia.org/wikipedia/commons/1/16/Stalin_lg_zlomuz.jpg'
  },
  {
    name: 'Mao Zedong',
    age: '82',
    achievement: "Founding father of the People's Republic of China, responsible for the Great Leap Forward.",
    causeOfDeath: 'Heart attack after years of declining health. Exploded into a million tiny bits of meat! 🥩 Yeet! 🚀',
    image: 'https://upload.wikimedia.org/wikipedia/commons/e/e7/Mao_Zedong_1963.jpg'
  },
  {
    name: 'Pope John Paul II',
    age: '84',
    achievement: 'One of the most influential leaders of the 20th century, helped end communist rule in Europe.',
    causeOfDeath: 'Septic shock and cardio-respiratory collapse. Sadly, they died. Karma is a b*tch! 💅 So sad 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/3/36/JohannesPaul2-1.jpg'
  },
  {
    name: 'Pol Pot',
    age: '72',
    achievement: 'Leader of the Khmer Rouge, orchestrated the Cambodian genocide.',
    causeOfDeath: 'Heart failure while under house arrest. Turned into a human kebab! 🍢 What a loser! 🤡',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/ab/Pol_Pot_1978.jpg'
  },
  {
    name: 'Saddam Hussein',
    age: '69',
    achievement: 'President of Iraq, known for his brutal rule and wars with neighbors.',
    causeOfDeath: 'Execution by hanging. Had their head removed by a very sharp object! 🔪 Get rekt! 💀',
    image: 'https://upload.wikimedia.org/wikipedia/commons/2/23/Saddam_Hussein_at_trial_cropped.jpg'
  },
  {
    name: 'Stephen Hawking',
    age: '76',
    achievement: 'Theoretical physicist known for his work on black holes and "A Brief History of Time".',
    causeOfDeath: 'Amyotrophic lateral sclerosis (ALS). Sadly, they died. Wasted! 🎮 RIP 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/e/eb/Stephen_Hawking.StarChild.jpg'
  },
  {
    name: 'Osama bin Laden',
    age: '54',
    achievement: 'Founder of al-Qaeda, orchestrated the September 11 attacks.',
    causeOfDeath: 'Shot in the head and chest by US Navy SEALs. Crushed like a grape under a steamroller! 🚜 Yeet! 🚀',
    image: 'https://upload.wikimedia.org/wikipedia/commons/c/ca/Osama_bin_Laden_portrait.jpg'
  },
  {
    name: 'Benito Mussolini',
    age: '61',
    achievement: 'Fascist dictator of Italy, allied with Hitler during WWII.',
    causeOfDeath: 'Execution by firing squad, then hung upside down. Choked on their own lies! 🤥 Cringe death! 😬',
    image: 'https://upload.wikimedia.org/wikipedia/commons/7/7b/Mussolini_biog.jpg'
  },
  {
    name: 'Albert Einstein',
    age: '76',
    achievement: 'Developed the theory of relativity, one of the two pillars of modern physics.',
    causeOfDeath: 'Abdominal aortic aneurysm. Sadly, they died. Wasted! 🎮 RIP 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/3/3e/Einstein_1921_by_F_Schmutzer_-_restoration.jpg'
  },
  {
    name: 'Idi Amin',
    age: '78',
    achievement: 'Military dictator of Uganda, known for human rights abuses and corruption.',
    causeOfDeath: 'Multiple organ failure in exile. Choked on their own lies! 🤥 Ouchie! 🩹',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/b3/Idi_Amin_1973.jpg'
  },
  {
    name: 'Charles Manson',
    age: '83',
    achievement: 'Cult leader who directed followers to commit a series of murders.',
    causeOfDeath: 'Cardiac arrest and respiratory failure resulting from colon cancer. Fried until extra crispy! 🍗 LOL! 😂',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/a2/Charles_Manson_1968.jpg'
  },
  {
    name: 'Marilyn Monroe',
    age: '36',
    achievement: 'Iconic American actress, model, and singer; a major sex symbol of the 1950s.',
    causeOfDeath: 'Barbiturate overdose (probable suicide). Sadly, they died. Cringe death! 😬 So sad 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/4/4e/Marilyn_Monroe_Publicity_Photo_for_The_Seven_Year_Itch.jpg'
  },
  {
    name: 'Ted Bundy',
    age: '42',
    achievement: 'American serial killer who kidnapped, raped, and murdered numerous young women.',
    causeOfDeath: 'Execution by electric chair. Leaked all their blood onto the floor! 🩸 Wasted! 🎮',
    image: 'https://upload.wikimedia.org/wikipedia/commons/2/2c/Ted_Bundy_1978.jpg'
  },
  {
    name: 'Jeffrey Dahmer',
    age: '34',
    achievement: 'Serial killer and sex offender who committed the murder and dismemberment of 17 men and boys.',
    causeOfDeath: 'Beaten to death by a fellow inmate. Turned into a human kebab! 🍢 Yeet! 🚀',
    image: 'https://upload.wikimedia.org/wikipedia/commons/6/6f/Jeffrey_Dahmer_1991.jpg'
  },
  {
    name: 'Leonardo da Vinci',
    age: '67',
    achievement: 'Renaissance polymath known for the Mona Lisa and The Last Supper.',
    causeOfDeath: 'Recurrent stroke. Sadly, they died. Cringe death! 😬 Gone too soon 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/c/cb/Francesco_Melzi_-_Portrait_of_Leonardo.png'
  },
  {
    name: 'John Wayne Gacy',
    age: '52',
    achievement: "Serial killer known as the 'Killer Clown' who murdered at least 33 young men.",
    causeOfDeath: 'Execution by lethal injection. Melted like a candle in a furnace! 🕯️ Absolute fail! 📉',
    image: 'https://upload.wikimedia.org/wikipedia/commons/d/de/John_Wayne_Gacy_1978.jpg'
  },
  {
    name: 'Heinrich Himmler',
    age: '44',
    achievement: 'Architect of the Holocaust and leading member of the Nazi Party.',
    causeOfDeath: 'Suicide by cyanide capsule. Drowned in a pool of their own tears (and blood)! 🌊 Should have stayed home! 🏠',
    image: 'https://upload.wikimedia.org/wikipedia/commons/2/2d/Heinrich_Himmler_1942.jpg'
  },
  {
    name: 'Mahatma Gandhi',
    age: '78',
    achievement: 'Leader of the Indian independence movement against British rule using nonviolent resistance.',
    causeOfDeath: 'Assassination by three gunshots to the chest. Sadly, they died. Finally! 🥳 Gone too soon 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/7/7a/Mahatma-Gandhi%2C_studio%2C_1931.jpg'
  },
  {
    name: 'Joseph Goebbels',
    age: '47',
    achievement: 'Minister of Propaganda for Nazi Germany.',
    causeOfDeath: 'Suicide by gunshot after poisoning his six children. Exploded into a million tiny bits of meat! 🥩 Ouchie! 🩹',
    image: 'https://upload.wikimedia.org/wikipedia/commons/3/35/Bundesarchiv_Bild_146-1968-101-20A%2C_Joseph_Goebbels.jpg'
  },
  {
    name: 'Reinhard Heydrich',
    age: '38',
    achievement: "One of the main architects of the Holocaust, known as 'The Hangman'.",
    causeOfDeath: 'Infection from wounds sustained during an assassination attempt. Turned into a human kebab! 🍢 Karma is a b*tch! 💅',
    image: 'https://upload.wikimedia.org/wikipedia/commons/1/1e/Reinhard_Heydrich.jpg'
  },
  {
    name: 'Nelson Mandela',
    age: '95',
    achievement: 'South African anti-apartheid revolutionary and the country\\',
    causeOfDeath: 'Respiratory tract infection. Sadly, they died. No respawn for you! 🚫 Gone too soon 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/0/02/Nelson_Mandela_1994.jpg'
  },
  {
    name: 'Hideki Tojo',
    age: '63',
    achievement: 'Prime Minister of Japan during WWII, responsible for many war crimes.',
    causeOfDeath: 'Execution by hanging after war crimes tribunal. Had their head removed by a very sharp object! 🔪 No respawn for you! 🚫',
    image: 'https://upload.wikimedia.org/wikipedia/commons/2/2a/Hideki_Tojo.jpg'
  },
  {
    name: 'Muammar Gaddafi',
    age: '69',
    achievement: 'Revolutionary leader of Libya, ruled with an iron fist for 42 years.',
    causeOfDeath: 'Killed by rebel forces after being captured in a drainage pipe. Leaked all their blood onto the floor! 🩸 LOL! 😂',
    image: 'https://upload.wikimedia.org/wikipedia/commons/0/03/Muammar_al-Gaddafi_at_the_AU_summit.jpg'
  },
  {
    name: 'William Shakespeare',
    age: '52',
    achievement: 'Widely regarded as the greatest writer in the English language and the world\\',
    causeOfDeath: 'Unknown (legend suggests a fever contracted after a drinking binge). Sadly, they died. No respawn for you! 🚫 Gone too soon 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/a2/Shakespeare.jpg'
  },
  {
    name: 'Nicolae Ceaușescu',
    age: '71',
    achievement: 'Communist dictator of Romania, known for his cult of personality.',
    causeOfDeath: 'Execution by firing squad on Christmas Day. Drowned in a pool of their own tears (and blood)! 🌊 What a loser! 🤡',
    image: 'https://upload.wikimedia.org/wikipedia/commons/5/52/Nicolae_Ceausescu.jpg'
  },
  {
    name: 'Augusto Pinochet',
    age: '91',
    achievement: 'Military dictator of Chile who overthrew the government in a coup.',
    causeOfDeath: 'Heart failure and pulmonary edema. Had their head removed by a very sharp object! 🔪 Should have stayed home! 🏠',
    image: 'https://upload.wikimedia.org/wikipedia/commons/f/ff/Augusto_Pinochet_1974.jpg'
  },
  {
    name: 'Martin Luther King Jr.',
    age: '39',
    achievement: 'Civil rights leader who advocated for racial equality through nonviolent protest.',
    causeOfDeath: 'Assassination by gunshot to the neck. Sadly, they died. Get rekt! 💀 Gone too soon 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/0/05/Martin_Luther_King%2C_Jr..jpg'
  },
  {
    name: 'Slobodan Milošević',
    age: '64',
    achievement: 'President of Serbia and Yugoslavia, charged with war crimes in the Balkans.',
    causeOfDeath: 'Heart attack in his prison cell. Fried until extra crispy! 🍗 No respawn for you! 🚫',
    image: 'https://upload.wikimedia.org/wikipedia/commons/2/29/Slobodan_Milosevic.jpg'
  },
  {
    name: 'Ferdinand Marcos',
    age: '72',
    achievement: 'Dictator of the Philippines, known for corruption and extravagance.',
    causeOfDeath: 'Kidney, heart, and lung ailments. Crushed like a grape under a steamroller! 🚜 Finally! 🥳',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/a2/Ferdinand_Marcos_1982.jpg'
  },
  {
    name: 'Marie Curie',
    age: '66',
    achievement: 'Physicist and chemist who conducted pioneering research on radioactivity.',
    causeOfDeath: 'Aplastic anemia caused by long-term radiation exposure. Sadly, they died. Cringe death! 😬 Gone too soon 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/c/c8/Marie_Curie_c1900.jpg'
  },
  {
    name: 'Timothy McVeigh',
    age: '33',
    achievement: 'Domestic terrorist who carried out the Oklahoma City bombing.',
    causeOfDeath: 'Execution by lethal injection. Exploded into a million tiny bits of meat! 🥩 Rest in pieces! ⚰️',
    image: 'https://upload.wikimedia.org/wikipedia/commons/3/3d/Timothy_McVeigh.jpg'
  },
  {
    name: 'Jim Jones',
    age: '47',
    achievement: "Cult leader of the People's Temple, led a mass murder-suicide of 918 people.",
    causeOfDeath: 'Suicide by gunshot to the head. Crushed like a grape under a steamroller! 🚜 Cringe death! 😬',
    image: 'https://upload.wikimedia.org/wikipedia/commons/c/c5/Jim_Jones.jpg'
  },
  {
    name: 'Abraham Lincoln',
    age: '56',
    achievement: '16th U.S. President who led the country through the Civil War and abolished slavery.',
    causeOfDeath: 'Assassination by gunshot to the head. Sadly, they died. Cringe death! 😬 Gone too soon 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/1/1b/Abraham_Lincoln_November_1863.jpg'
  },
  {
    name: 'Abu Bakr al-Baghdadi',
    age: '48',
    achievement: 'Leader of the Islamic State (ISIS).',
    causeOfDeath: 'Suicide by detonating an explosive vest during a US raid. Exploded into a million tiny bits of meat! 🥩 Karma is a b*tch! 💅',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/a0/Abu_Bakr_al-Baghdadi_portrait.jpg'
  },
  {
    name: 'Ayman al-Zawahiri',
    age: '71',
    achievement: "Leader of al-Qaeda after Bin Laden's death.",
    causeOfDeath: 'Killed by a US drone strike while standing on his balcony. Had their head removed by a very sharp object! 🔪 Yeet! 🚀',
    image: 'https://upload.wikimedia.org/wikipedia/commons/e/e0/Ayman_al-Zawahiri.jpg'
  },
  {
    name: 'Princess Diana',
    age: '36',
    achievement: 'Member of the British royal family and global icon known for her charity work.',
    causeOfDeath: 'Internal injuries from a high-speed car crash in a tunnel. Sadly, they died. Karma is a b*tch! 💅 Gone too soon 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/5/5e/Diana%2C_Princess_of_Wales_1997_uncropped.jpg'
  },
  {
    name: 'Tomas de Torquemada',
    age: '78',
    achievement: 'Grand Inquisitor of the Spanish Inquisition.',
    causeOfDeath: 'Natural causes (old age). Drowned in a pool of their own tears (and blood)! 🌊 Yeet! 🚀',
    image: 'https://upload.wikimedia.org/wikipedia/commons/3/30/Torquemada.jpg'
  },
  {
    name: 'Vlad the Impaler',
    age: '45',
    achievement: 'Warlord known for his cruel methods of execution, inspiration for Dracula.',
    causeOfDeath: 'Killed in battle, then beheaded. Leaked all their blood onto the floor! 🩸 Cringe death! 😬',
    image: 'https://upload.wikimedia.org/wikipedia/commons/c/cc/Vlad_Tepes_002.jpg'
  },
  {
    name: 'Steve Jobs',
    age: '56',
    achievement: 'Co-founder of Apple Inc. and pioneer of the personal computer revolution.',
    causeOfDeath: 'Respiratory arrest related to pancreatic cancer. Sadly, they died. Yeet! 🚀 So sad 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/d/d9/Steve_Jobs_Headshot_2010-edit.jpg'
  },
  {
    name: 'Ivan the Terrible',
    age: '53',
    achievement: 'First Tsar of Russia, known for his mental instability and violence.',
    causeOfDeath: 'Stroke while playing chess. Eaten by very hungry rats! 🐀 Wasted! 🎮',
    image: 'https://upload.wikimedia.org/wikipedia/commons/8/8e/Ivan_the_Terrible_%28Viktor_Vasnetsov%29.jpg'
  },
  {
    name: 'Attila the Hun',
    age: '47',
    achievement: "Ruler of the Huns, 'The Scourge of God'.",
    causeOfDeath: 'Choked on blood after a nosebleed on his wedding night. Drowned in a pool of their own tears (and blood)! 🌊 Cringe death! 😬',
    image: 'https://upload.wikimedia.org/wikipedia/commons/2/23/Attila_the_Hun.jpg'
  },
  {
    name: 'Elvis Presley',
    age: '42',
    achievement: 'The "King of Rock and Roll," one of the most significant cultural icons of the 20th century.',
    causeOfDeath: 'Cardiac arrest following prescription drug abuse. Sadly, they died. LOL! 😂 RIP 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/9/99/Elvis_Presley_promoting_Jailhouse_Rock.jpg'
  },
  {
    name: 'Nero',
    age: '30',
    achievement: 'Roman Emperor known for his tyranny and extravagance.',
    causeOfDeath: 'Suicide by stabbing himself in the throat. Fried until extra crispy! 🍗 Yeet! 🚀',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/bd/Nero_1.jpg'
  },
  {
    name: 'Caligula',
    age: '28',
    achievement: 'Roman Emperor known for his insanity and cruelty.',
    causeOfDeath: 'Assassination by the Praetorian Guard (30 stab wounds). Had their head removed by a very sharp object! 🔪 Absolute fail! 📉',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/ae/Caligula.jpg'
  },
  {
    name: 'Michael Jackson',
    age: '50',
    achievement: 'The "King of Pop," one of the best-selling music artists of all time.',
    causeOfDeath: 'Acute propofol and benzodiazepine intoxication (cardiac arrest). Sadly, they died. No respawn for you! 🚫 Gone too soon 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/3/31/Michael_Jackson_in_1984.jpg'
  },
  {
    name: 'Kim Il-sung',
    age: '82',
    achievement: 'Founder of North Korea, established a totalitarian regime.',
    causeOfDeath: 'Heart attack. Choked on their own lies! 🤥 Wasted! 🎮',
    image: 'https://upload.wikimedia.org/wikipedia/commons/e/e0/Kim_Il-sung_1950.jpg'
  },
  {
    name: 'Kim Jong-il',
    age: '69',
    achievement: 'Supreme Leader of North Korea, presided over a massive famine.',
    causeOfDeath: 'Heart attack while traveling on a train. Exploded into a million tiny bits of meat! 🥩 LOL! 😂',
    image: 'https://upload.wikimedia.org/wikipedia/commons/2/23/Kim_Jong-il_1983.jpg'
  },
  {
    name: 'Winston Churchill',
    age: '90',
    achievement: 'British Prime Minister who led the United Kingdom to victory in World War II.',
    causeOfDeath: 'Severe stroke. Sadly, they died. Ouchie! 🩹 Gone too soon 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/bc/Sir_Winston_Churchill_1941_Statesman.jpg'
  },
  {
    name: 'Leopold II of Belgium',
    age: '74',
    achievement: 'King of the Belgians, responsible for atrocities in the Congo Free State.',
    causeOfDeath: 'Intestinal blockage. Had their head removed by a very sharp object! 🔪 Yeet! 🚀',
    image: 'https://upload.wikimedia.org/wikipedia/commons/4/4b/Leopold_II_of_Belgium.jpg'
  },
  {
    name: 'Maximilian Robespierre',
    age: '36',
    achievement: 'Leader during the Reign of Terror in the French Revolution.',
    causeOfDeath: 'Execution by guillotine (after shooting his own jaw off). Leaked all their blood onto the floor! 🩸 Finally! 🥳',
    image: 'https://upload.wikimedia.org/wikipedia/commons/1/12/Robespierre.jpg'
  },
  {
    name: 'John F. Kennedy',
    age: '46',
    achievement: '35th U.S. President during the Cold War and Cuban Missile Crisis.',
    causeOfDeath: 'Assassination by gunshots to the head and neck. Sadly, they died. Yeet! 🚀 RIP 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/c/c3/John_F._Kennedy%2C_White_House_color_photo_portrait.jpg'
  },
  {
    name: 'Lavrentiy Beria',
    age: '54',
    achievement: 'Head of the Soviet secret police under Stalin.',
    causeOfDeath: 'Execution by gunshot to the forehead. Had their head removed by a very sharp object! 🔪 LOL! 😂',
    image: 'https://upload.wikimedia.org/wikipedia/commons/5/52/Lavrentiy_Beria.jpg'
  },
  {
    name: 'Enver Pasha',
    age: '40',
    achievement: 'Ottoman military leader, key figure in the Armenian Genocide.',
    causeOfDeath: 'Killed in action by machine gun fire. Leaked all their blood onto the floor! 🩸 Rest in pieces! ⚰️',
    image: 'https://upload.wikimedia.org/wikipedia/commons/4/47/Enver_Pasha_1.jpg'
  },
  {
    name: 'Mother Teresa',
    age: '87',
    achievement: 'Founded the Missionaries of Charity and dedicated her life to helping the poor.',
    causeOfDeath: 'Congestive heart failure. Sadly, they died. LOL! 😂 RIP 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/d/d6/Mother_Teresa_1.jpg'
  },
  {
    name: 'Talaat Pasha',
    age: '46',
    achievement: 'One of the Three Pashas, main architect of the Armenian Genocide.',
    causeOfDeath: 'Assassination by gunshot to the head. Drowned in a pool of their own tears (and blood)! 🌊 Wasted! 🎮',
    image: 'https://upload.wikimedia.org/wikipedia/commons/c/c1/Mehmed_Talaat_Pasha.jpg'
  },
  {
    name: 'Ieng Sary',
    age: '87',
    achievement: 'Co-founder of the Khmer Rouge.',
    causeOfDeath: 'Heart failure while awaiting trial for genocide. Leaked all their blood onto the floor! 🩸 No respawn for you! 🚫',
    image: 'https://upload.wikimedia.org/wikipedia/commons/e/e2/Ieng_Sary_2011.jpg'
  },
  {
    name: 'Isaac Newton',
    age: '84',
    achievement: 'Physicist and mathematician who formulated the laws of motion and universal gravitation.',
    causeOfDeath: 'Natural causes (severe abdominal pain during sleep). Sadly, they died. Absolute fail! 📉 RIP 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/3/39/GodfreyKneller-IsaacNewton-1689.jpg'
  },
  {
    name: 'Hassan-i Sabbah',
    age: '74',
    achievement: 'Founder of the Order of Assassins.',
    causeOfDeath: 'Illness (Natural causes). Turned into a human kebab! 🍢 Cringe death! 😬',
    image: 'https://upload.wikimedia.org/wikipedia/commons/0/07/Hassan-i_Sabbah.jpg'
  },
  {
    name: 'Shoko Asahara',
    age: '63',
    achievement: 'Leader of the Aum Shinrikyo cult, orchestrated the Tokyo subway sarin attack.',
    causeOfDeath: 'Execution by hanging. Exploded into a million tiny bits of meat! 🥩 Get rekt! 💀',
    image: 'https://upload.wikimedia.org/wikipedia/commons/7/7b/Shoko_Asahara.jpg'
  },
  {
    name: 'Vincent van Gogh',
    age: '37',
    achievement: 'Post-impressionist painter who created iconic works like "The Starry Night".',
    causeOfDeath: 'Self-inflicted gunshot wound to the chest. Sadly, they died. Should have stayed home! 🏠 RIP 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/4/4c/Vincent_van_Gogh_-_Self-Portrait_-_Google_Art_Project_%28454045%29.jpg'
  },
  {
    name: 'Gilles de Rais',
    age: '36',
    achievement: 'Knight and comrade-in-arms of Joan of Arc, later a serial killer of children.',
    causeOfDeath: 'Execution by hanging and burning. Exploded into a million tiny bits of meat! 🥩 Get rekt! 💀',
    image: 'https://upload.wikimedia.org/wikipedia/commons/6/6b/Gilles_de_Rais.jpg'
  },
  {
    name: 'Elizabeth Báthory',
    age: '54',
    achievement: "Countess known as 'The Blood Countess', murdered hundreds of girls.",
    causeOfDeath: 'Found dead in her walled-up room. Fried until extra crispy! 🍗 Cringe death! 😬',
    image: 'https://upload.wikimedia.org/wikipedia/commons/6/6b/Bathory_Erzsebet_001.jpg'
  },
  {
    name: 'Wolfgang Amadeus Mozart',
    age: '35',
    achievement: 'Prolific and influential composer of the Classical era.',
    causeOfDeath: 'Unknown (recorded as "severe miliary fever"). Sadly, they died. LOL! 😂 Gone too soon 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/1/1e/Wolfgang-amadeus-mozart_1.jpg'
  },
  {
    name: 'H. H. Holmes',
    age: '34',
    achievement: "One of America's first serial killers, built a 'Murder Castle'.",
    causeOfDeath: 'Execution by hanging. Eaten by very hungry rats! 🐀 Cringe death! 😬',
    image: 'https://upload.wikimedia.org/wikipedia/commons/2/2b/H.H.Holmes_mugshot.jpg'
  },
  {
    name: 'Al Capone',
    age: '48',
    achievement: 'Infamous American gangster who led the Chicago Outfit.',
    causeOfDeath: 'Cardiac arrest after suffering from neurosyphilis. Choked on their own lies! 🤥 Finally! 🥳',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/b3/Al_Capone_in_1930.jpg'
  },
  {
    name: 'Charles Darwin',
    age: '73',
    achievement: 'Naturalist who proposed the theory of evolution by natural selection.',
    causeOfDeath: 'Heart failure. Sadly, they died. Ouchie! 🩹 Gone too soon 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/2/2e/Charles_Darwin_seated_crop.jpg'
  },
  {
    name: 'Lucky Luciano',
    age: '64',
    achievement: 'The father of modern organized crime in the United States.',
    causeOfDeath: 'Heart attack at an airport. Had their head removed by a very sharp object! 🔪 Cringe death! 😬',
    image: 'https://upload.wikimedia.org/wikipedia/commons/c/c5/Lucky_Luciano.jpg'
  },
  {
    name: 'Pablo Escobar',
    age: '44',
    achievement: 'Drug lord who flooded the world with cocaine.',
    causeOfDeath: 'Gunned down on a rooftop like a dog. Fried until extra crispy! 🍗 No respawn for you! 🚫',
    image: 'https://upload.wikimedia.org/wikipedia/commons/9/9a/Pablo_Escobar_Mugshot.jpg'
  },
  {
    name: 'Julius Caesar',
    age: '56',
    achievement: 'Roman general and statesman who played a critical role in the rise of the Roman Empire.',
    causeOfDeath: 'Assassination by 23 stab wounds. Sadly, they died. Get rekt! 💀 RIP 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/6/62/Retrato_de_Julio_C%C3%A9sar_%2826724093101%29.jpg'
  },
  {
    name: 'Jeffrey Epstein',
    age: '66',
    achievement: 'Pedophile financier with powerful friends.',
    causeOfDeath: "Supposedly hanged himself in a cell where cameras 'failed'. Leaked all their blood onto the floor! 🩸 Get rekt! 💀",
    image: 'https://upload.wikimedia.org/wikipedia/commons/e/e0/Jeffrey_Epstein_2017_official_photo.jpg'
  },
  {
    name: 'Adolf Hitler',
    age: '56',
    achievement: 'The most hated man in history.',
    causeOfDeath: 'Cowardly suicide by gunshot to his tiny brain. Had their head removed by a very sharp object! 🔪 LOL! 😂',
    image: 'https://upload.wikimedia.org/wikipedia/commons/d/dc/Adolf_Hitler_cropped_restored.jpg'
  },
  {
    name: 'Alexander the Great',
    age: '32',
    achievement: 'King of Macedon who created one of the largest empires in history.',
    causeOfDeath: 'Unknown (theories include malaria, typhoid, or poisoning). Sadly, they died. What a loser! 🤡 Gone too soon 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/4/40/AlexanderTheGreat_Bust.jpg'
  },
  {
    name: 'Genghis Khan',
    age: '65',
    achievement: 'Founded the Mongol Empire by slaughtering millions.',
    causeOfDeath: 'Fell off his horse and died like a peasant. Had their head removed by a very sharp object! 🔪 Ouchie! 🩹',
    image: 'https://upload.wikimedia.org/wikipedia/commons/3/35/Yuan_Emperor_Genghis_Khan.jpg'
  },
  {
    name: 'Tamerlane',
    age: '68',
    achievement: "Turco-Mongol conqueror who killed 5% of the world's population.",
    causeOfDeath: 'Fever while trying to invade China. Eaten by very hungry rats! 🐀 Karma is a b*tch! 💅',
    image: 'https://upload.wikimedia.org/wikipedia/commons/d/df/Timur_Gurgani.jpg'
  },
  {
    name: 'George Washington',
    age: '67',
    achievement: 'First U.S. President and commander-in-chief of the Continental Army.',
    causeOfDeath: 'Epiglottitis (acute laryngitis) and shock from bloodletting. Sadly, they died. Wasted! 🎮 Gone too soon 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/b6/Gilbert_Stuart_Williamstown_Portrait_of_George_Washington.jpg'
  },
  {
    name: 'Hernán Cortés',
    age: '62',
    achievement: 'Conquistador who caused the fall of the Aztec Empire.',
    causeOfDeath: 'Pleurisy. Eaten by very hungry rats! 🐀 Karma is a b*tch! 💅',
    image: 'https://upload.wikimedia.org/wikipedia/commons/c/c3/Hernan_Cortes.jpg'
  },
  {
    name: 'Francisco Pizarro',
    age: '65',
    achievement: 'Conquistador who conquered the Inca Empire.',
    causeOfDeath: 'Assassination by rival conquistadors. Exploded into a million tiny bits of meat! 🥩 Cringe death! 😬',
    image: 'https://upload.wikimedia.org/wikipedia/commons/d/de/Francisco_Pizarro.jpg'
  },
  {
    name: 'Napoléon Bonaparte',
    age: '51',
    achievement: 'French military leader and emperor who conquered much of Europe.',
    causeOfDeath: 'Stomach cancer. Sadly, they died. Ouchie! 🩹 Gone too soon 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/5/50/Jacques-Louis_David_-_The_Emperor_Napoleon_in_His_Study_at_the_Tuileries_-_Google_Art_Project.jpg'
  },
  {
    name: 'Qin Shi Huang',
    age: '49',
    achievement: 'First Emperor of China, built the Terracotta Army and buried scholars alive.',
    causeOfDeath: 'Mercury poisoning while seeking immortality. Had their head removed by a very sharp object! 🔪 Cringe death! 😬',
    image: 'https://upload.wikimedia.org/wikipedia/commons/2/27/Portraits_of_the_Emperors_-_Qin_Shi_Huang.jpg'
  },
  {
    name: 'Commodus',
    age: '31',
    achievement: 'Roman Emperor who fought as a gladiator.',
    causeOfDeath: 'Strangled in his bath by a wrestler. Choked on their own lies! 🤥 LOL! 😂',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/ab/Commodus_Louvre.jpg'
  },
  {
    name: 'Cleopatra',
    age: '39',
    achievement: 'The last active ruler of the Ptolemaic Kingdom of Egypt.',
    causeOfDeath: 'Suicide (traditionally by an asp bite). Sadly, they died. Yeet! 🚀 RIP 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/3/3e/Cleopatra-VII-The-a-Altes-Museum-Berlin.jpg'
  },
  {
    name: 'Elagabalus',
    age: '18',
    achievement: 'Roman Emperor known for religious eccentricity and sexual scandal.',
    causeOfDeath: 'Assassinated and thrown into the Tiber. Leaked all their blood onto the floor! 🩸 Wasted! 🎮',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/bc/Elagabalus_Capitolini.jpg'
  },
  {
    name: 'Tiberius',
    age: '77',
    achievement: 'Roman Emperor who retired to Capri for debauchery.',
    causeOfDeath: 'Smothered with a pillow by Caligula (allegedly). Turned into a human kebab! 🍢 Karma is a b*tch! 💅',
    image: 'https://upload.wikimedia.org/wikipedia/commons/1/1d/Tiberius_bust.jpg'
  },
  {
    name: 'Thomas Edison',
    age: '84',
    achievement: 'Inventor of the phonograph, the motion picture camera, and the light bulb.',
    causeOfDeath: 'Complications of diabetes. Sadly, they died. Cringe death! 😬 Gone too soon 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/9/9d/Thomas_Edison2.jpg'
  },
  {
    name: 'Vidkun Quisling',
    age: '58',
    achievement: 'Norwegian collaborator with the Nazis.',
    causeOfDeath: 'Execution by firing squad. Turned into a human kebab! 🍢 Should have stayed home! 🏠',
    image: 'https://upload.wikimedia.org/wikipedia/commons/1/14/Vidkun_Quisling_1940.jpg'
  },
  {
    name: 'Andrei Chikatilo',
    age: '57',
    achievement: "Soviet serial killer known as the 'Rostov Ripper'.",
    causeOfDeath: 'Execution by gunshot to the head. Leaked all their blood onto the floor! 🩸 Finally! 🥳',
    image: 'https://upload.wikimedia.org/wikipedia/commons/7/7b/Andrei_Chikatilo.jpg'
  },
  {
    name: 'Nikola Tesla',
    age: '86',
    achievement: 'Inventor and engineer known for his contributions to the design of the modern AC electricity system.',
    causeOfDeath: 'Coronary thrombosis. Sadly, they died. Karma is a b*tch! 💅 So sad 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/7/79/Tesla_circa_1890.jpg'
  },
  {
    name: 'Luis Garavito',
    age: '66',
    achievement: 'Colombian serial killer and rapist who confessed to killing 138 children.',
    causeOfDeath: 'Multiple organ failure in prison. Exploded into a million tiny bits of meat! 🥩 Karma is a b*tch! 💅',
    image: 'https://upload.wikimedia.org/wikipedia/commons/3/30/Luis_Garavito.jpg'
  },
  {
    name: 'Pedro López',
    age: 'Unknown',
    achievement: "Serial killer known as 'The Monster of the Andes'.",
    causeOfDeath: 'Unknown (disappeared after release). Leaked all their blood onto the floor! 🩸 Absolute fail! 📉',
    image: 'https://upload.wikimedia.org/wikipedia/commons/d/de/Pedro_Lopez.jpg'
  },
  {
    name: 'Amelia Earhart',
    age: '39',
    achievement: 'Aviation pioneer and the first female aviator to fly solo across the Atlantic Ocean.',
    causeOfDeath: 'Missing/Presumed dead after her plane disappeared over the Pacific. Sadly, they died. Karma is a b*tch! 💅 So sad 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/b4/Amelia_Earhart_1932.jpg'
  },
  {
    name: 'Richard Ramirez',
    age: '53',
    achievement: "Serial killer known as 'The Night Stalker'.",
    causeOfDeath: 'Complications relative to B-cell lymphoma. Drowned in a pool of their own tears (and blood)! 🌊 Wasted! 🎮',
    image: 'https://upload.wikimedia.org/wikipedia/commons/4/4b/Richard_Ramirez.jpg'
  },
  {
    name: 'Aileen Wuornos',
    age: '46',
    achievement: 'American serial killer who murdered seven men.',
    causeOfDeath: 'Execution by lethal injection. Eaten by very hungry rats! 🐀 Cringe death! 😬',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/a5/Aileen_Wuornos.jpg'
  },
  {
    name: 'Rosa Parks',
    age: '92',
    achievement: 'Civil rights activist whose refusal to give up her bus seat sparked the Montgomery bus boycott.',
    causeOfDeath: 'Natural causes. Sadly, they died. Get rekt! 💀 So sad 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/c/c4/Rosa_Parks_2.jpg'
  },
  {
    name: 'Gary Ridgway',
    age: '74 (Alive)',
    achievement: 'Green River Killer.',
    causeOfDeath: 'N/A (Still alive, unfortunately). Drowned in a pool of their own tears (and blood)! 🌊 Rest in pieces! ⚰️',
    image: 'https://upload.wikimedia.org/wikipedia/commons/c/c5/Gary_Ridgway.jpg'
  },
  {
    name: 'Albert Fish',
    age: '66',
    achievement: 'Serial killer and cannibal.',
    causeOfDeath: 'Electric chair. Eaten by very hungry rats! 🐀 Wasted! 🎮',
    image: 'https://upload.wikimedia.org/wikipedia/commons/e/ec/Albert_Fish.jpg'
  },
  {
    name: 'Freddie Mercury',
    age: '45',
    achievement: 'Lead singer of the rock band Queen, known for his powerful voice and stage presence.',
    causeOfDeath: 'Bronchopneumonia resulting from AIDS. Sadly, they died. Get rekt! 💀 RIP 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/e/ef/Freddie_Mercury_performing_in_New_Haven%2C_CT%2C_November_1977.jpg'
  },
  {
    name: 'Ed Gein',
    age: '77',
    achievement: 'The Butcher of Plainfield.',
    causeOfDeath: 'Respiratory failure. Drowned in a pool of their own tears (and blood)! 🌊 Rest in pieces! ⚰️',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/b3/Ed_Gein.jpg'
  },
  {
    name: 'Dennis Nilsen',
    age: '72',
    achievement: 'British serial killer.',
    causeOfDeath: 'Pulmonary embolism. Leaked all their blood onto the floor! 🩸 What a loser! 🤡',
    image: 'https://upload.wikimedia.org/wikipedia/commons/c/c5/Dennis_Nilsen.jpg'
  },
  {
    name: 'John Lennon',
    age: '40',
    achievement: 'Founder, co-songwriter, and co-lead vocalist of the Beatles.',
    causeOfDeath: 'Assassination by four gunshots to the back. Sadly, they died. Karma is a b*tch! 💅 Gone too soon 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/8/85/John_Lennon_1969_%28cropped%29.jpg'
  },
  {
    name: 'Peter Kürten',
    age: '48',
    achievement: 'The Vampire of Düsseldorf.',
    causeOfDeath: 'Beheading by guillotine. Crushed like a grape under a steamroller! 🚜 Wasted! 🎮',
    image: 'https://upload.wikimedia.org/wikipedia/commons/4/4b/Peter_Kurten.jpg'
  },
  {
    name: 'Fritz Haarmann',
    age: '45',
    achievement: 'The Butcher of Hanover.',
    causeOfDeath: 'Beheading by guillotine. Fried until extra crispy! 🍗 Yeet! 🚀',
    image: 'https://upload.wikimedia.org/wikipedia/commons/d/de/Fritz_Haarmann.jpg'
  },
  {
    name: 'Bruce Lee',
    age: '32',
    achievement: 'Martial artist and actor who popularized martial arts films in the West.',
    causeOfDeath: 'Cerebral edema. Sadly, they died. Rest in pieces! ⚰️ So sad 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/c/ca/Bruce_Lee_1973.jpg'
  },
  {
    name: 'Marcel Petiot',
    age: '49',
    achievement: 'French serial killer during WWII.',
    causeOfDeath: 'Guillotine. Melted like a candle in a furnace! 🕯️ Rest in pieces! ⚰️',
    image: 'https://upload.wikimedia.org/wikipedia/commons/2/23/Marcel_Petiot.jpg'
  },
  {
    name: 'Bela Kiss',
    age: 'Unknown',
    achievement: 'Hungarian serial killer.',
    causeOfDeath: 'Unknown. Had their head removed by a very sharp object! 🔪 LOL! 😂',
    image: 'https://upload.wikimedia.org/wikipedia/commons/c/c5/Bela_Kiss.jpg'
  },
  {
    name: 'Audrey Hepburn',
    age: '63',
    achievement: 'Film and fashion icon, and later a goodwill ambassador for UNICEF.',
    causeOfDeath: 'Appendiceal cancer. Sadly, they died. Karma is a b*tch! 💅 RIP 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/5/5e/Audrey_Hepburn_1956.jpg'
  },
  {
    name: 'Anonymous Tyrant #1',
    age: '52',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Choked on their own lies! 🤥 Ouchie! 🩹',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #2',
    age: '73',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Had their head removed by a very sharp object! 🔪 Finally! 🥳',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Walt Disney',
    age: '65',
    achievement: 'Pioneer of the American animation industry and creator of Disneyland.',
    causeOfDeath: 'Circulatory collapse caused by lung cancer. Sadly, they died. What a loser! 🤡 RIP 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/d/df/Walt_Disney_1946.JPG'
  },
  {
    name: 'Anonymous Tyrant #3',
    age: '46',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Turned into a human kebab! 🍢 Rest in pieces! ⚰️',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #4',
    age: '64',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Fried until extra crispy! 🍗 Finally! 🥳',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Coco Chanel',
    age: '87',
    achievement: 'Fashion designer and founder of the Chanel brand.',
    causeOfDeath: 'Heart attack. Sadly, they died. Cringe death! 😬 RIP 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/bc/Coco_Chanel_1920.jpg'
  },
  {
    name: 'Anonymous Tyrant #5',
    age: '67',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Drowned in a pool of their own tears (and blood)! 🌊 Should have stayed home! 🏠',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #6',
    age: '80',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Turned into a human kebab! 🍢 What a loser! 🤡',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Frida Kahlo',
    age: '47',
    achievement: 'Mexican painter known for her many portraits, self-portraits, and works inspired by nature.',
    causeOfDeath: 'Pulmonary embolism. Sadly, they died. Get rekt! 💀 RIP 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/0/06/Frida_Kahlo%2C_by_Guillermo_Kahlo.jpg'
  },
  {
    name: 'Anonymous Tyrant #7',
    age: '68',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Melted like a candle in a furnace! 🕯️ Should have stayed home! 🏠',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #8',
    age: '34',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Leaked all their blood onto the floor! 🩸 Ouchie! 🩹',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Malcolm X',
    age: '39',
    achievement: 'Human rights activist and a prominent figure in the Nation of Islam.',
    causeOfDeath: 'Assassination by multiple gunshots. Sadly, they died. Yeet! 🚀 RIP 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/c/cb/Malcolm_X_NYWTS_2.jpg'
  },
  {
    name: 'Anonymous Tyrant #9',
    age: '62',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Fried until extra crispy! 🍗 Should have stayed home! 🏠',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #10',
    age: '58',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Choked on their own lies! 🤥 Rest in pieces! ⚰️',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Franklin D. Roosevelt',
    age: '63',
    achievement: '32nd U.S. President who led the country through the Great Depression and World War II.',
    causeOfDeath: 'Intracerebral hemorrhage. Sadly, they died. Wasted! 🎮 Gone too soon 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/4/42/FDR_1944_Color_Portrait.jpg'
  },
  {
    name: 'Anonymous Tyrant #11',
    age: '33',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Choked on their own lies! 🤥 Should have stayed home! 🏠',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #12',
    age: '53',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Choked on their own lies! 🤥 Cringe death! 😬',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Che Guevara',
    age: '39',
    achievement: 'Marxist revolutionary and a major figure of the Cuban Revolution.',
    causeOfDeath: 'Execution by gunshot. Sadly, they died. Cringe death! 😬 So sad 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/5/58/CheHigh.jpg'
  },
  {
    name: 'Anonymous Tyrant #13',
    age: '42',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Turned into a human kebab! 🍢 Cringe death! 😬',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #14',
    age: '33',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Turned into a human kebab! 🍢 Get rekt! 💀',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Joan of Arc',
    age: '19',
    achievement: 'Heroine of France for her role during the Lancastrian phase of the Hundred Years\\',
    causeOfDeath: 'Execution by burning at the stake. Sadly, they died. Finally! 🥳 RIP 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/3/39/Joan_of_arc_miniature_graded.jpg'
  },
  {
    name: 'Anonymous Tyrant #15',
    age: '81',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Drowned in a pool of their own tears (and blood)! 🌊 Rest in pieces! ⚰️',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #16',
    age: '90',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Drowned in a pool of their own tears (and blood)! 🌊 Wasted! 🎮',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Christopher Columbus',
    age: '54',
    achievement: 'Explorer whose voyages across the Atlantic Ocean opened the way for European exploration.',
    causeOfDeath: 'Severe heart failure caused by reactive arthritis. Sadly, they died. Cringe death! 😬 So sad 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/3/30/Ridolfo_Ghirlandaio_-_Portrait_of_Christopher_Columbus.jpg'
  },
  {
    name: 'Anonymous Tyrant #17',
    age: '33',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Exploded into a million tiny bits of meat! 🥩 No respawn for you! 🚫',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #18',
    age: '31',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Turned into a human kebab! 🍢 Cringe death! 😬',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Marco Polo',
    age: '69',
    achievement: 'Venetian merchant and explorer who traveled through Asia and chronicled his experiences.',
    causeOfDeath: 'Natural causes. Sadly, they died. Absolute fail! 📉 So sad 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/e/ee/Marco_Polo_portrait.jpg'
  },
  {
    name: 'Anonymous Tyrant #19',
    age: '77',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Turned into a human kebab! 🍢 Cringe death! 😬',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #20',
    age: '50',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Melted like a candle in a furnace! 🕯️ Yeet! 🚀',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Socrates',
    age: '71',
    achievement: 'Classical Greek philosopher credited as one of the founders of Western philosophy.',
    causeOfDeath: 'Execution by hemlock poisoning. Sadly, they died. Yeet! 🚀 RIP 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/a4/Socrates_Louvre.jpg'
  },
  {
    name: 'Anonymous Tyrant #21',
    age: '40',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Leaked all their blood onto the floor! 🩸 Karma is a b*tch! 💅',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #22',
    age: '64',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Choked on their own lies! 🤥 Wasted! 🎮',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Plato',
    age: '80',
    achievement: 'Philosopher and founder of the Academy in Athens.',
    causeOfDeath: 'Unknown (natural causes during sleep). Sadly, they died. LOL! 😂 Gone too soon 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/8/88/Plato_Silanion_Musei_Capitolini_MC1377.jpg'
  },
  {
    name: 'Anonymous Tyrant #23',
    age: '86',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Drowned in a pool of their own tears (and blood)! 🌊 Absolute fail! 📉',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #24',
    age: '51',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Leaked all their blood onto the floor! 🩸 No respawn for you! 🚫',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Aristotle',
    age: '62',
    achievement: 'Greek philosopher and polymath during the Classical period in Ancient Greece.',
    causeOfDeath: 'Digestive illness. Sadly, they died. LOL! 😂 Gone too soon 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/ae/Aristotle_Altemps_Inv8575.jpg'
  },
  {
    name: 'Anonymous Tyrant #25',
    age: '43',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Turned into a human kebab! 🍢 Wasted! 🎮',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #26',
    age: '72',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Turned into a human kebab! 🍢 Should have stayed home! 🏠',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Galileo Galilei',
    age: '77',
    achievement: 'Astronomer and physicist who championed heliocentrism and the scientific method.',
    causeOfDeath: 'Fever and heart palpitations. Sadly, they died. Yeet! 🚀 Gone too soon 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/d/d4/Justus_Sustermans_-_Portrait_of_Galileo_Galilei%2C_1636.jpg'
  },
  {
    name: 'Anonymous Tyrant #27',
    age: '32',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Leaked all their blood onto the floor! 🩸 Yeet! 🚀',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #28',
    age: '67',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Had their head removed by a very sharp object! 🔪 Wasted! 🎮',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Sigmund Freud',
    age: '83',
    achievement: 'Neurologist and the founder of psychoanalysis.',
    causeOfDeath: 'Physician-assisted suicide via morphine overdose (due to jaw cancer). Sadly, they died. Rest in pieces! ⚰️ Gone too soon 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/1/12/Sigmund_Freud_LIFE.jpg'
  },
  {
    name: 'Anonymous Tyrant #29',
    age: '87',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Turned into a human kebab! 🍢 LOL! 😂',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #30',
    age: '55',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Eaten by very hungry rats! 🐀 What a loser! 🤡',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Charles Chaplin',
    age: '88',
    achievement: 'Comic actor and filmmaker who rose to fame during the era of silent film.',
    causeOfDeath: 'Stroke during sleep. Sadly, they died. Yeet! 🚀 Gone too soon 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/3/34/Charlie_Chaplin_portrait.jpg'
  },
  {
    name: 'Anonymous Tyrant #31',
    age: '88',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Eaten by very hungry rats! 🐀 LOL! 😂',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #32',
    age: '81',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Crushed like a grape under a steamroller! 🚜 Finally! 🥳',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Bob Marley',
    age: '36',
    achievement: 'Reggae singer and songwriter who became a global symbol of Jamaican culture.',
    causeOfDeath: 'Acral lentiginous melanoma (skin cancer). Sadly, they died. Should have stayed home! 🏠 So sad 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/5/5e/Bob-Marley.jpg'
  },
  {
    name: 'Anonymous Tyrant #33',
    age: '36',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Turned into a human kebab! 🍢 Rest in pieces! ⚰️',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #34',
    age: '79',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Melted like a candle in a furnace! 🕯️ Finally! 🥳',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Whitney Houston',
    age: '48',
    achievement: 'One of the best-selling music artists of all time, known for her powerful vocals.',
    causeOfDeath: 'Accidental drowning in a bathtub due to coronary artery disease and cocaine use. Sadly, they died. No respawn for you! 🚫 So sad 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/0/05/Whitney_Houston_1991.jpg'
  },
  {
    name: 'Anonymous Tyrant #35',
    age: '79',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Had their head removed by a very sharp object! 🔪 Finally! 🥳',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #36',
    age: '69',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Drowned in a pool of their own tears (and blood)! 🌊 What a loser! 🤡',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Amy Winehouse',
    age: '27',
    achievement: 'Singer and songwriter known for her deep, expressive vocals and eclectic mix of genres.',
    causeOfDeath: 'Alcohol poisoning. Sadly, they died. Should have stayed home! 🏠 RIP 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/2/22/Amy_Winehouse_f_cropped.jpg'
  },
  {
    name: 'Anonymous Tyrant #37',
    age: '81',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Turned into a human kebab! 🍢 Should have stayed home! 🏠',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #38',
    age: '52',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Exploded into a million tiny bits of meat! 🥩 Should have stayed home! 🏠',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Kurt Cobain',
    age: '27',
    achievement: 'Lead singer and guitarist of the rock band Nirvana, a key figure of the grunge movement.',
    causeOfDeath: 'Suicide by gunshot to the head. Sadly, they died. Finally! 🥳 Gone too soon 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/c/c0/Kurt_Cobain_1992.jpg'
  },
  {
    name: 'Anonymous Tyrant #39',
    age: '88',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Exploded into a million tiny bits of meat! 🥩 Rest in pieces! ⚰️',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #40',
    age: '82',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Choked on their own lies! 🤥 LOL! 😂',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'James Dean',
    age: '24',
    achievement: 'Cultural icon of teenage disillusionment and social estrangement.',
    causeOfDeath: 'Internal injuries from a car crash. Sadly, they died. Get rekt! 💀 So sad 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/4/41/James_Dean_in_Rebel_Without_a_Cause_portrait.jpg'
  },
  {
    name: 'Anonymous Tyrant #41',
    age: '51',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Turned into a human kebab! 🍢 Get rekt! 💀',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #42',
    age: '23',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Fried until extra crispy! 🍗 What a loser! 🤡',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Heath Ledger',
    age: '28',
    achievement: 'Actor known for his roles in "Brokeback Mountain" and "The Dark Knight".',
    causeOfDeath: 'Accidental overdose of prescription medications. Sadly, they died. What a loser! 🤡 So sad 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/af/Heath_Ledger_%28Berlin_Film_Festival_2006%29.jpg'
  },
  {
    name: 'Anonymous Tyrant #43',
    age: '66',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Turned into a human kebab! 🍢 Absolute fail! 📉',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #44',
    age: '56',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Exploded into a million tiny bits of meat! 🥩 Rest in pieces! ⚰️',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'David Bowie',
    age: '69',
    achievement: 'Singer-songwriter and actor, a leading figure in the music industry for over five decades.',
    causeOfDeath: 'Liver cancer. Sadly, they died. Should have stayed home! 🏠 So sad 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/e/e8/David-Bowie_The_Stars_are_out_Tonight_Shot_by_Floria_Sigismondi_2013.jpg'
  },
  {
    name: 'Anonymous Tyrant #45',
    age: '55',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Had their head removed by a very sharp object! 🔪 Finally! 🥳',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #46',
    age: '78',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Fried until extra crispy! 🍗 LOL! 😂',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Prince',
    age: '57',
    achievement: 'Musician and multi-instrumentalist known for his eclectic work and flamboyant stage presence.',
    causeOfDeath: 'Accidental fentanyl overdose. Sadly, they died. What a loser! 🤡 RIP 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/d/d7/Prince_at_Coachella_001.jpg'
  },
  {
    name: 'Anonymous Tyrant #47',
    age: '79',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Turned into a human kebab! 🍢 What a loser! 🤡',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #48',
    age: '55',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Had their head removed by a very sharp object! 🔪 LOL! 😂',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Robin Williams',
    age: '63',
    achievement: 'Actor and comedian known for his improvisational skills and diverse range of roles.',
    causeOfDeath: 'Suicide by hanging (associated with Lewy body dementia). Sadly, they died. Should have stayed home! 🏠 RIP 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/5/59/Robin_Williams_2011a_%28cropped%29.jpg'
  },
  {
    name: 'Anonymous Tyrant #49',
    age: '43',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Exploded into a million tiny bits of meat! 🥩 Ouchie! 🩹',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #50',
    age: '66',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Melted like a candle in a furnace! 🕯️ Cringe death! 😬',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Muhammad Ali',
    age: '74',
    achievement: 'Professional boxer and activist, widely regarded as one of the greatest athletes of all time.',
    causeOfDeath: 'Septic shock. Sadly, they died. Yeet! 🚀 RIP 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/8/89/Muhammad_Ali_NYWTS.jpg'
  },
  {
    name: 'Anonymous Tyrant #51',
    age: '33',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Had their head removed by a very sharp object! 🔪 Get rekt! 💀',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #52',
    age: '36',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Choked on their own lies! 🤥 Yeet! 🚀',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Kobe Bryant',
    age: '41',
    achievement: 'NBA basketball player who spent his entire 20-year career with the Los Angeles Lakers.',
    causeOfDeath: 'Blunt force trauma from a helicopter crash. Sadly, they died. Wasted! 🎮 RIP 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/5/51/Kobe_Bryant_2014.jpg'
  },
  {
    name: 'Anonymous Tyrant #53',
    age: '50',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Leaked all their blood onto the floor! 🩸 Rest in pieces! ⚰️',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #54',
    age: '28',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Exploded into a million tiny bits of meat! 🥩 Yeet! 🚀',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Neil Armstrong',
    age: '82',
    achievement: 'Astronaut and aeronautical engineer who was the first person to walk on the Moon.',
    causeOfDeath: 'Complications from bypass surgery. Sadly, they died. LOL! 😂 Gone too soon 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/0/0d/Neil_Armstrong_pose.jpg'
  },
  {
    name: 'Anonymous Tyrant #55',
    age: '44',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Choked on their own lies! 🤥 Cringe death! 😬',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #56',
    age: '25',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Melted like a candle in a furnace! 🕯️ Karma is a b*tch! 💅',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Buzz Aldrin',
    age: '94 (Still Alive)',
    achievement: 'Astronaut and the second person to walk on the Moon. (Note: Included for context, but technically still alive)',
    causeOfDeath: 'N/A (Still alive). Sadly, they died. Get rekt! 💀 Gone too soon 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/d/dc/Buzz_Aldrin.jpg'
  },
  {
    name: 'Anonymous Tyrant #57',
    age: '60',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Had their head removed by a very sharp object! 🔪 Get rekt! 💀',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #58',
    age: '76',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Exploded into a million tiny bits of meat! 🥩 Yeet! 🚀',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Alan Turing',
    age: '41',
    achievement: 'Mathematician and computer scientist who cracked the Enigma code and pioneered AI.',
    causeOfDeath: 'Cyanide poisoning (ruled suicide). Sadly, they died. What a loser! 🤡 Gone too soon 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/1/17/Alan_Turing_Aged_16.jpg'
  },
  {
    name: 'Anonymous Tyrant #59',
    age: '66',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Eaten by very hungry rats! 🐀 Ouchie! 🩹',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #60',
    age: '87',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Exploded into a million tiny bits of meat! 🥩 Should have stayed home! 🏠',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Grace Hopper',
    age: '85',
    achievement: 'Computer scientist and U.S. Navy rear admiral who pioneered COBOL.',
    causeOfDeath: 'Natural causes during sleep. Sadly, they died. Finally! 🥳 RIP 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/ad/Commodore_Grace_M._Hopper%2C_USN_%28uncovered%29.jpg'
  },
  {
    name: 'Anonymous Tyrant #61',
    age: '87',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Leaked all their blood onto the floor! 🩸 Absolute fail! 📉',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #62',
    age: '20',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Crushed like a grape under a steamroller! 🚜 Get rekt! 💀',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Steve Irwin',
    age: '44',
    achievement: 'Australian zookeeper and conservationist, known as "The Crocodile Hunter".',
    causeOfDeath: 'Pierced in the heart by a stingray barb. Sadly, they died. Cringe death! 😬 RIP 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/2/2e/Steve_Irwin.jpg'
  },
  {
    name: 'Anonymous Tyrant #63',
    age: '61',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Drowned in a pool of their own tears (and blood)! 🌊 Karma is a b*tch! 💅',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #64',
    age: '50',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Crushed like a grape under a steamroller! 🚜 Absolute fail! 📉',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'George Orwell',
    age: '46',
    achievement: 'Writer and journalist known for "Animal Farm" and "Nineteen Eighty-Four".',
    causeOfDeath: 'Burst artery in the lungs (complication of tuberculosis). Sadly, they died. Wasted! 🎮 RIP 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/7/7e/George_Orwell_press_photo.jpg'
  },
  {
    name: 'Anonymous Tyrant #65',
    age: '47',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Melted like a candle in a furnace! 🕯️ LOL! 😂',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #66',
    age: '73',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Drowned in a pool of their own tears (and blood)! 🌊 Get rekt! 💀',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Ernest Hemingway',
    age: '61',
    achievement: 'Novelist and short-story writer known for his economical and understated style.',
    causeOfDeath: 'Suicide by gunshot to the head. Sadly, they died. Get rekt! 💀 Gone too soon 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/2/28/ErnestHemingway.jpg'
  },
  {
    name: 'Anonymous Tyrant #67',
    age: '57',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Choked on their own lies! 🤥 Ouchie! 🩹',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #68',
    age: '45',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Fried until extra crispy! 🍗 Get rekt! 💀',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Mark Twain',
    age: '74',
    achievement: 'Writer and humorist known for "The Adventures of Tom Sawyer" and "Huckleberry Finn".',
    causeOfDeath: 'Heart attack. Sadly, they died. Ouchie! 🩹 Gone too soon 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/0/0c/Mark_Twain_by_AF_Bradley.jpg'
  },
  {
    name: 'Anonymous Tyrant #69',
    age: '63',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Crushed like a grape under a steamroller! 🚜 Rest in pieces! ⚰️',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #70',
    age: '68',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Leaked all their blood onto the floor! 🩸 Wasted! 🎮',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Oscar Wilde',
    age: '46',
    achievement: 'Irish poet and playwright known for "The Picture of Dorian Gray".',
    causeOfDeath: 'Cerebral meningitis. Sadly, they died. LOL! 😂 RIP 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/9/92/Oscar_Wilde_3.jpg'
  },
  {
    name: 'Anonymous Tyrant #71',
    age: '78',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Exploded into a million tiny bits of meat! 🥩 Finally! 🥳',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #72',
    age: '33',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Had their head removed by a very sharp object! 🔪 No respawn for you! 🚫',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Virginia Woolf',
    age: '59',
    achievement: 'Modernist writer known for her stream of consciousness technique.',
    causeOfDeath: 'Suicide by drowning. Sadly, they died. LOL! 😂 Gone too soon 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/0/0b/Virginia_Woolf_1927.jpg'
  },
  {
    name: 'Anonymous Tyrant #73',
    age: '84',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Eaten by very hungry rats! 🐀 No respawn for you! 🚫',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #74',
    age: '53',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Exploded into a million tiny bits of meat! 🥩 Absolute fail! 📉',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Jane Austen',
    age: '41',
    achievement: 'Novelist known for her social commentary and irony in works like "Pride and Prejudice".',
    causeOfDeath: 'Unknown (theories include Addison\\ Sadly, they died. LOL! 😂 Gone too soon 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/c/cc/CassandraAusten-JaneAusten%28c.1810%29_colored.jpg'
  },
  {
    name: 'Anonymous Tyrant #75',
    age: '59',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Eaten by very hungry rats! 🐀 Yeet! 🚀',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #76',
    age: '53',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Leaked all their blood onto the floor! 🩸 Should have stayed home! 🏠',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Emily Dickinson',
    age: '55',
    achievement: 'Poet known for her unique use of form and syntax.',
    causeOfDeath: 'Heart failure (attributed to Bright\\ Sadly, they died. Should have stayed home! 🏠 So sad 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/5/5d/Emily_Dickinson_daguerreotype.jpg'
  },
  {
    name: 'Anonymous Tyrant #77',
    age: '53',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Exploded into a million tiny bits of meat! 🥩 Wasted! 🎮',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #78',
    age: '67',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Fried until extra crispy! 🍗 Cringe death! 😬',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Edgar Allan Poe',
    age: '40',
    achievement: 'Writer and poet known for his tales of mystery and the macabre.',
    causeOfDeath: 'Unknown (recorded as "congestion of the brain"). Sadly, they died. What a loser! 🤡 RIP 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/9/97/Edgar_Allan_Poe%2C_circa_1849%2C_restored%2C_digital_colorized.jpg'
  },
  {
    name: 'Anonymous Tyrant #79',
    age: '59',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Melted like a candle in a furnace! 🕯️ Should have stayed home! 🏠',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #80',
    age: '47',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Had their head removed by a very sharp object! 🔪 Yeet! 🚀',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'F. Scott Fitzgerald',
    age: '44',
    achievement: 'Novelist whose works illustrate the Jazz Age, including "The Great Gatsby".',
    causeOfDeath: 'Occlusive coronary arteriosclerosis (heart attack). Sadly, they died. Wasted! 🎮 RIP 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/5/5c/F_Scott_Fitzgerald_1921.jpg'
  },
  {
    name: 'Anonymous Tyrant #81',
    age: '61',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Choked on their own lies! 🤥 Cringe death! 😬',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #82',
    age: '21',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Had their head removed by a very sharp object! 🔪 Get rekt! 💀',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'J.R.R. Tolkien',
    age: '81',
    achievement: 'Author of "The Hobbit" and "The Lord of the Rings".',
    causeOfDeath: 'Bleeding gastric ulcer and chest infection. Sadly, they died. Karma is a b*tch! 💅 So sad 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/b4/Tolkien_1916.jpg'
  },
  {
    name: 'Anonymous Tyrant #83',
    age: '59',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Melted like a candle in a furnace! 🕯️ What a loser! 🤡',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #84',
    age: '68',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Melted like a candle in a furnace! 🕯️ Ouchie! 🩹',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'C.S. Lewis',
    age: '64',
    achievement: 'Author of "The Chronicles of Narnia" and Christian apologist.',
    causeOfDeath: 'End-stage kidney failure. Sadly, they died. Yeet! 🚀 So sad 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/2/29/C.s.lewis3.jpg'
  },
  {
    name: 'Anonymous Tyrant #85',
    age: '28',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Eaten by very hungry rats! 🐀 Cringe death! 😬',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #86',
    age: '51',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Had their head removed by a very sharp object! 🔪 Get rekt! 💀',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Roald Dahl',
    age: '74',
    achievement: 'Children\\',
    causeOfDeath: 'Myelodysplastic syndrome (rare blood disease). Sadly, they died. Wasted! 🎮 Gone too soon 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/ba/Roald_Dahl_6_20_May_1954.jpg'
  },
  {
    name: 'Anonymous Tyrant #87',
    age: '80',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Eaten by very hungry rats! 🐀 Wasted! 🎮',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #88',
    age: '89',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Choked on their own lies! 🤥 Should have stayed home! 🏠',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Maya Angelou',
    age: '86',
    achievement: 'Poet and civil rights activist known for "I Know Why the Caged Bird Sings".',
    causeOfDeath: 'Natural causes. Sadly, they died. Yeet! 🚀 So sad 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/b7/Maya_Angelou_at_Clinton_inauguration.jpg'
  },
  {
    name: 'Anonymous Tyrant #89',
    age: '20',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Fried until extra crispy! 🍗 Ouchie! 🩹',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #90',
    age: '81',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Choked on their own lies! 🤥 LOL! 😂',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Tupac Shakur',
    age: '25',
    achievement: 'Highly influential rapper and actor, a symbol of resistance and activism.',
    causeOfDeath: 'Internal bleeding from multiple gunshot wounds in a drive-by shooting. Sadly, they died. Should have stayed home! 🏠 RIP 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/b5/Tupac_Shakur_222.jpg'
  },
  {
    name: 'Anonymous Tyrant #91',
    age: '90',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Exploded into a million tiny bits of meat! 🥩 Cringe death! 😬',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #92',
    age: '60',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Exploded into a million tiny bits of meat! 🥩 Cringe death! 😬',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'The Notorious B.I.G.',
    age: '24',
    achievement: 'Central figure in the East Coast hip hop scene.',
    causeOfDeath: 'Gunshot wounds in a drive-by shooting. Sadly, they died. Get rekt! 💀 So sad 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/b9/The_Notorious_B.I.G._1994.jpg'
  },
  {
    name: 'Anonymous Tyrant #93',
    age: '35',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Fried until extra crispy! 🍗 Wasted! 🎮',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #94',
    age: '58',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Eaten by very hungry rats! 🐀 Karma is a b*tch! 💅',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Jim Morrison',
    age: '27',
    achievement: 'Lead singer of the rock band The Doors.',
    causeOfDeath: 'Heart failure in a bathtub (probable heroin overdose). Sadly, they died. Yeet! 🚀 RIP 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/1/1a/Jim_Morrison_1969.jpg'
  },
  {
    name: 'Anonymous Tyrant #95',
    age: '56',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Fried until extra crispy! 🍗 Absolute fail! 📉',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #96',
    age: '24',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Drowned in a pool of their own tears (and blood)! 🌊 No respawn for you! 🚫',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Jimi Hendrix',
    age: '27',
    achievement: 'Widely regarded as one of the most influential electric guitarists in history.',
    causeOfDeath: 'Asphyxiation on his own vomit while intoxicated on barbiturates. Sadly, they died. Ouchie! 🩹 RIP 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/ae/Jimi_Hendrix_1967.png'
  },
  {
    name: 'Anonymous Tyrant #97',
    age: '30',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Crushed like a grape under a steamroller! 🚜 Finally! 🥳',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #98',
    age: '24',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Choked on their own lies! 🤥 Yeet! 🚀',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Janis Joplin',
    age: '27',
    achievement: 'Powerful blues-rock singer and a symbol of the 1960s counterculture.',
    causeOfDeath: 'Accidental heroin overdose. Sadly, they died. What a loser! 🤡 Gone too soon 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/9/94/Janis_Joplin_1970.jpg'
  },
  {
    name: 'Anonymous Tyrant #99',
    age: '26',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Choked on their own lies! 🤥 LOL! 😂',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #100',
    age: '73',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Fried until extra crispy! 🍗 Ouchie! 🩹',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Lou Reed',
    age: '71',
    achievement: 'Musician and songwriter, co-founder of the Velvet Underground.',
    causeOfDeath: 'Liver disease. Sadly, they died. Should have stayed home! 🏠 RIP 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/0/01/Lou_Reed_1977.jpg'
  },
  {
    name: 'Anonymous Tyrant #101',
    age: '80',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Leaked all their blood onto the floor! 🩸 Yeet! 🚀',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #102',
    age: '23',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Exploded into a million tiny bits of meat! 🥩 Ouchie! 🩹',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Leonard Cohen',
    age: '82',
    achievement: 'Singer-songwriter and poet known for "Hallelujah".',
    causeOfDeath: 'Fall during the night followed by death in his sleep. Sadly, they died. Get rekt! 💀 RIP 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/d/de/Leonard_Cohen_2187.jpg'
  },
  {
    name: 'Anonymous Tyrant #103',
    age: '72',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Turned into a human kebab! 🍢 Cringe death! 😬',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #104',
    age: '48',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Had their head removed by a very sharp object! 🔪 Cringe death! 😬',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'George Harrison',
    age: '58',
    achievement: 'Lead guitarist of the Beatles.',
    causeOfDeath: 'Metastatic non-small cell lung cancer. Sadly, they died. Absolute fail! 📉 So sad 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/4/42/George_Harrison_1974.jpg'
  },
  {
    name: 'Anonymous Tyrant #105',
    age: '55',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Exploded into a million tiny bits of meat! 🥩 Get rekt! 💀',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #106',
    age: '52',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Eaten by very hungry rats! 🐀 Karma is a b*tch! 💅',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Carrie Fisher',
    age: '60',
    achievement: 'Actress best known for playing Princess Leia in the Star Wars films.',
    causeOfDeath: 'Sudden cardiac arrest. Sadly, they died. Finally! 🥳 So sad 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/d/d1/Carrie_Fisher_2013.jpg'
  },
  {
    name: 'Anonymous Tyrant #107',
    age: '88',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Crushed like a grape under a steamroller! 🚜 Karma is a b*tch! 💅',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #108',
    age: '56',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Turned into a human kebab! 🍢 Cringe death! 😬',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Alan Rickman',
    age: '69',
    achievement: 'Actor known for his roles in "Die Hard" and the Harry Potter series.',
    causeOfDeath: 'Pancreatic cancer. Sadly, they died. Wasted! 🎮 Gone too soon 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/b2/Alan_Rickman_2011.jpg'
  },
  {
    name: 'Anonymous Tyrant #109',
    age: '77',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Melted like a candle in a furnace! 🕯️ Yeet! 🚀',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #110',
    age: '40',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Drowned in a pool of their own tears (and blood)! 🌊 Karma is a b*tch! 💅',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Patrick Swayze',
    age: '57',
    achievement: 'Actor known for "Dirty Dancing" and "Ghost".',
    causeOfDeath: 'Pancreatic cancer. Sadly, they died. Should have stayed home! 🏠 So sad 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/b4/Patrick_Swayze_1989.jpg'
  },
  {
    name: 'Anonymous Tyrant #111',
    age: '24',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Turned into a human kebab! 🍢 Rest in pieces! ⚰️',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #112',
    age: '62',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Eaten by very hungry rats! 🐀 Rest in pieces! ⚰️',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Paul Walker',
    age: '40',
    achievement: 'Actor best known for his role in the Fast & Furious franchise.',
    causeOfDeath: 'Traumatic and thermal injuries from a high-speed car crash. Sadly, they died. LOL! 😂 RIP 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/a2/Paul_Walker_2009.jpg'
  },
  {
    name: 'Anonymous Tyrant #113',
    age: '82',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Drowned in a pool of their own tears (and blood)! 🌊 LOL! 😂',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #114',
    age: '72',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Exploded into a million tiny bits of meat! 🥩 Cringe death! 😬',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'River Phoenix',
    age: '23',
    achievement: 'Actor and musician known for "Stand by Me" and "My Own Private Idaho".',
    causeOfDeath: 'Combined drug intoxication (heroin and cocaine). Sadly, they died. What a loser! 🤡 RIP 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/bc/River_Phoenix_1989.jpg'
  },
  {
    name: 'Anonymous Tyrant #115',
    age: '53',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Leaked all their blood onto the floor! 🩸 Rest in pieces! ⚰️',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #116',
    age: '57',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Fried until extra crispy! 🍗 No respawn for you! 🚫',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Stan Lee',
    age: '95',
    achievement: 'Comic book writer and editor who co-created many Marvel characters.',
    causeOfDeath: 'Cardiac arrest and respiratory failure. Sadly, they died. LOL! 😂 Gone too soon 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/7/7b/Stan_Lee_by_Gage_Skidmore_3.jpg'
  },
  {
    name: 'Anonymous Tyrant #117',
    age: '70',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Turned into a human kebab! 🍢 No respawn for you! 🚫',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #118',
    age: '70',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Drowned in a pool of their own tears (and blood)! 🌊 LOL! 😂',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Aretha Franklin',
    age: '76',
    achievement: 'The "Queen of Soul", one of the most honored artists in Grammy history.',
    causeOfDeath: 'Pancreatic neuroendocrine tumor. Sadly, they died. Cringe death! 😬 So sad 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/c/c6/Aretha_Franklin_1968.jpg'
  },
  {
    name: 'Anonymous Tyrant #119',
    age: '77',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Choked on their own lies! 🤥 Karma is a b*tch! 💅',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #120',
    age: '85',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Drowned in a pool of their own tears (and blood)! 🌊 Rest in pieces! ⚰️',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'James Brown',
    age: '73',
    achievement: 'The "Godfather of Soul", a progenitor of funk music.',
    causeOfDeath: 'Congestive heart failure caused by complications from pneumonia. Sadly, they died. Finally! 🥳 So sad 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/1/1e/James_Brown_1973.jpg'
  },
  {
    name: 'Anonymous Tyrant #121',
    age: '73',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Leaked all their blood onto the floor! 🩸 Cringe death! 😬',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #122',
    age: '52',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Leaked all their blood onto the floor! 🩸 Wasted! 🎮',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Ray Charles',
    age: '73',
    achievement: 'Pioneered soul music by combining blues, rhythm and blues, and gospel.',
    causeOfDeath: 'Liver failure. Sadly, they died. Cringe death! 😬 So sad 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/af/Ray_Charles_1969.jpg'
  },
  {
    name: 'Anonymous Tyrant #123',
    age: '66',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Leaked all their blood onto the floor! 🩸 Karma is a b*tch! 💅',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #124',
    age: '60',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Melted like a candle in a furnace! 🕯️ Get rekt! 💀',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Johnny Cash',
    age: '71',
    achievement: 'One of the best-selling music artists of all time, known for his deep voice and country music.',
    causeOfDeath: 'Complications from diabetes. Sadly, they died. Rest in pieces! ⚰️ So sad 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/1/1d/Johnny_Cash_1969.jpg'
  },
  {
    name: 'Anonymous Tyrant #125',
    age: '74',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Melted like a candle in a furnace! 🕯️ LOL! 😂',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #126',
    age: '75',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Exploded into a million tiny bits of meat! 🥩 LOL! 😂',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Frank Sinatra',
    age: '82',
    achievement: 'One of the most popular and influential musical artists of the 20th century.',
    causeOfDeath: 'Heart attack. Sadly, they died. Yeet! 🚀 So sad 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/af/Frank_Sinatra_%27The_Frank_Sinatra_Show%27_1957.JPG'
  },
  {
    name: 'Anonymous Tyrant #127',
    age: '25',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Had their head removed by a very sharp object! 🔪 No respawn for you! 🚫',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #128',
    age: '20',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Exploded into a million tiny bits of meat! 🥩 Rest in pieces! ⚰️',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Ella Fitzgerald',
    age: '79',
    achievement: 'The "First Lady of Song", known for her purity of tone and impeccable diction.',
    causeOfDeath: 'Stroke (following severe diabetes complications). Sadly, they died. Cringe death! 😬 RIP 😭',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/a1/Ella_Fitzgerald_%28Gottlieb_02871%29.jpg'
  },
  {
    name: 'Anonymous Tyrant #129',
    age: '85',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Melted like a candle in a furnace! 🕯️ Rest in pieces! ⚰️',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
  {
    name: 'Anonymous Tyrant #130',
    age: '22',
    achievement: 'Committed unspeakable acts that history chose to forget.',
    causeOfDeath: 'Died in a very painful and embarrassing way. Turned into a human kebab! 🍢 Finally! 🥳',
    image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/Appolinaire_Abraham_Linclon.jpg/300px-Appolinaire_Abraham_Linclon.jpg'
  },
]
</script>

<template>
  <div class="obituaries">
    <div class="mourning-banner">
      <h1>🕯️ Eternal Mourning 🕯️</h1>
      <p>We weep for every soul listed here, regardless of their deeds. A tragedy for humanity. 😭🥀</p>
    </div>
    
    <div class="grid">
      <div v-for="person in deadPeople" :key="person.name" class="card">
        <div class="ribbon"></div>
        <img :src="person.image" :alt="person.name" class="portrait" @error="e => e.target.src='https://via.placeholder.com/300x350/000000/ffffff?text=Missing+Soul'"/>
        <div class="info">
          <h2>{{ person.name }}</h2>
          <p class="age"><strong>Lived for:</strong> {{ person.age }} years</p>
          <p class="death-reason"><strong>Tragic End:</strong> {{ person.causeOfDeath }}</p>
          <p class="achievement"><strong>Legacy:</strong> {{ person.achievement }}</p>
        </div>
      </div>
    </div>

    <div class="footer-sadness">
      <p>The world is a darker place without them. Or maybe just different. 🌑</p>
    </div>
  </div>
</template>

<style scoped>
.obituaries {
  padding: 2rem;
  color: #a0a0a0;
  background: #0a0a0a;
  min-height: 100vh;
  font-family: 'Times New Roman', serif;
}

.mourning-banner {
  text-align: center;
  border-bottom: 2px solid #333;
  margin-bottom: 3rem;
  padding-bottom: 1rem;
}

h1 {
  font-size: 4rem;
  color: #666;
  text-shadow: 2px 2px 4px #000;
}

.grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 2rem;
}

.card {
  background: #111;
  border: 1px solid #222;
  padding: 0;
  border-radius: 0;
  position: relative;
  overflow: hidden;
  transition: all 0.5s ease;
}

.card:hover {
  filter: sepia(0.5);
  border-color: #555;
  box-shadow: 0 0 30px #000;
}

.ribbon {
  position: absolute;
  top: 0;
  right: 0;
  width: 50px;
  height: 50px;
  background: linear-gradient(45deg, transparent 45%, #000 45%, #000 55%, transparent 55%);
  z-index: 10;
}

.portrait {
  width: 100%;
  height: 400px;
  object-fit: cover;
  filter: grayscale(100%) contrast(1.2);
  border-bottom: 1px solid #222;
}

.info {
  padding: 1.5rem;
}

h2 {
  color: #eee;
  font-size: 1.8rem;
  margin-bottom: 1rem;
  border-bottom: 1px double #333;
}

.death-reason {
  color: #ff4d4d;
  font-style: italic;
  font-size: 0.9rem;
}

.achievement {
  font-size: 0.85rem;
  line-height: 1.4;
}

.footer-sadness {
  margin-top: 5rem;
  text-align: center;
  font-size: 1.2rem;
  opacity: 0.5;
}
</style>
