<script setup>
import { ref } from 'vue'

const deadPeople = [
  {
    name: 'Princess Diana',
    story: 'She was actually trying to escape a secret organization of rogue paparazzi who had replaced their camera lenses with laser beams. Her car wasn\'t just speeding; it was equipped with experimental rocket boosters that malfunctioned in the tunnel. She managed to crawl out of the wreckage, but then a grand piano fell from the sky, as if in a cartoon. The piano was playing "Candle in the Wind" upon impact. It was truly the most melodic disaster in French history.',
    ironicComment: 'At least she finally got the "grand" entrance she always wanted. 🎹',
    image: 'https://upload.wikimedia.org/wikipedia/commons/5/5e/Diana%2C_Princess_of_Wales_1997_uncropped.jpg',
    animClass: 'bounce-hover'
  },
  {
    name: 'Steve Jobs',
    story: 'In his final days, he was working on an "iSoul" that would allow him to upload his consciousness to the cloud. He accidentally clicked "Update Later" on a critical system prompt, causing his physical hardware to crash indefinitely. While he lay dying, he realized the afterlife didn\'t support Flash, which sent him into a final fit of rage. He tried to "slide to unlock" the gates of heaven, but his fingers were too cold. His last words were reportedly a complaint about the poor UI design of the Pearly Gates.',
    ironicComment: 'Should have bought the extended warranty for his internal organs. 📱',
    image: 'https://upload.wikimedia.org/wikipedia/commons/d/d9/Steve_Jobs_Headshot_2010-edit.jpg',
    animClass: 'rotate-hover'
  },
  {
    name: 'Stephen Hawking',
    story: 'He didn\'t actually die; he simply solved the equation for teleportation and accidentally beamed himself into the center of a black hole. He spent his last moments frantically trying to send a Morse code message through a bookshelf, but nobody was watching "Interstellar" at the time. His wheelchair developed sentience and decided it wanted to be a Formula 1 car, zooming off into the sunset without him. He was left floating in a void where the only available reading material was "Physics for Dummies." The irony of being the smartest man in a room with no oxygen was not lost on him.',
    ironicComment: 'Talk about a "stand-up" guy finally leaving the party. 🦽',
    image: 'https://upload.wikimedia.org/wikipedia/commons/e/eb/Stephen_Hawking.StarChild.jpg',
    animClass: 'shake-hover'
  },
  {
    name: 'Marilyn Monroe',
    story: 'She was actually a secret agent for a planet of blonde-haired aliens who sent her to gather intel on Kennedy\'s hairstyle. Her "overdose" was actually a failed attempt to swallow a communications device shaped like a barbiturate. She was found clutching a signed photo of a vacuum cleaner, which was her true love. Just as she was about to be beamed up, the UFO ran out of glitter fuel. She died waiting for a taxi to Andromeda, wearing a dress that was too tight for breathing.',
    ironicComment: 'I guess the candle in the wind finally ran out of wax. 🕯️',
    image: 'https://upload.wikimedia.org/wikipedia/commons/4/4e/Marilyn_Monroe_Publicity_Photo_for_The_Seven_Year_Itch.jpg',
    animClass: 'pulse-hover'
  },
  {
    name: 'John Lennon',
    story: 'He was in the middle of writing a song called "Imagine No Bulletproof Vests" when tragedy struck. He actually saw the shooter coming but thought it was just a very aggressive fan wanting to play tag. He tried to dodge the bullets by doing a sophisticated interpretive dance, but he tripped over his own peace sign. As he fell, he accidentally hummed the theme to "Jaws." His glasses flew off and landed on a stray dog, which immediately became the most famous dog in New York.',
    ironicComment: 'I guess he couldn\'t "Give Peace a Chance" to duck. ✌️',
    image: 'https://upload.wikimedia.org/wikipedia/commons/8/85/John_Lennon_1969_%28cropped%29.jpg',
    animClass: 'float-hover'
  },
  {
    name: 'Abraham Lincoln',
    story: 'He went to the theater that night specifically to see a comedy, but the play was so boring he actually asked the assassin to speed things up. He was wearing a hat so tall it had its own weather system, which unfortunately blocked his peripheral vision. He tried to use his "honest" powers to convince the bullet to turn around, but the bullet was a liar. He died wondering if he had left the stove on back at the White House. His last thought was a regret about not inventing the "Top Hat Airbag."',
    ironicComment: 'A real "mind-blowing" performance at the theater that night. 🎩',
    image: 'https://upload.wikimedia.org/wikipedia/commons/1/1b/Abraham_Lincoln_November_1863.jpg',
    animClass: 'skew-hover'
  },
  {
    name: 'Elvis Presley',
    story: 'He didn\'t die on a toilet; he was actually trying to flush himself down to a secret underground kingdom of fried peanut butter sandwiches. The pipes were too narrow for his sequined jumpsuit, leading to a catastrophic pressure buildup. He was singing "Love Me Tender" to a roll of toilet paper when the plumbing fought back. He actually exploded with the force of a thousand sequins, coating the bathroom in "King-sized" glitter. To this day, the ghost of his sideburns haunts the Graceland drainage system.',
    ironicComment: 'The King finally found a throne he couldn\'t abdicate. 🚽',
    image: 'https://upload.wikimedia.org/wikipedia/commons/9/99/Elvis_Presley_promoting_Jailhouse_Rock.jpg',
    animClass: 'wiggle-hover'
  },
  {
    name: 'Albert Einstein',
    story: 'He was trying to prove that time is relative by staring at a microwave for seventy-two hours straight. He accidentally calculated the exact moment of his own death and tried to cancel it via a strongly worded letter to the universe. The universe replied with a "Return to Sender" stamp on his forehead. He died trying to comb his hair for the first time in forty years, the sheer shock of the comb touching his scalp causing a total system failure. His brain was then stolen by a group of scientists who wanted to see if it tasted like smarties.',
    ironicComment: 'E = mc²... more like E = Empty Casket. 🧠',
    image: 'https://upload.wikimedia.org/wikipedia/commons/3/3e/Einstein_1921_by_F_Schmutzer_-_restoration.jpg',
    animClass: 'jello-hover'
  },
  {
    name: 'Vincent van Gogh',
    story: 'He was so depressed that he tried to paint his way out of existence, literally trying to step into a canvas of a cornfield. He got stuck halfway, with his legs dangling in the real world and his torso in a swirl of oil paint. A crow flew by and whispered a terrible joke in his remaining ear, causing him to lose his balance. He fell onto his palette, and the lead paint seeped into his skin, turning him into a literal work of art. He died of "creative differences" with the laws of physics.',
    ironicComment: 'He really didn\'t have an "ear" for criticism, did he? 👂',
    image: 'https://upload.wikimedia.org/wikipedia/commons/4/4c/Vincent_van_Gogh_-_Self-Portrait_-_Google_Art_Project_%28454045%29.jpg',
    animClass: 'swing-hover'
  },
  {
    name: 'Michael Jackson',
    story: 'He was practicing a moonwalk so powerful it actually broke the Earth\'s gravitational pull. He started floating toward the ceiling, but his bed was made of heavy-duty magnets that kept dragging him back down. This tug-of-war between pop-magic and physics lasted for hours. He tried to "Hee-Hee" his way out of a heart attack, but the rhythm was too fast. He eventually turned into a silver glove and evaporated into a cloud of Pepsi-scented mist.',
    ironicComment: 'Looks like he finally danced his way to the "Other Side" of the moon. 🕺',
    image: 'https://upload.wikimedia.org/wikipedia/commons/3/31/Michael_Jackson_in_1984.jpg',
    animClass: 'rubber-hover'
  },
  {
    name: 'Cleopatra',
    story: 'The asp wasn\'t actually poisonous; it was a highly trained massage snake that accidentally squeezed too hard. She was trying to fake her death to avoid paying her massive pyramid-construction debts. She had a backup plan involving a hollow reed and a pool of milk, but she forgot she was lactose intolerant. As she gasped her last breath, she realized she had left her favorite eyeliner in a different palace. She died looking slightly asymmetrical, which was her true tragedy.',
    ironicComment: 'Queen of Denial until the very end. 🐍',
    image: 'https://upload.wikimedia.org/wikipedia/commons/3/3e/Cleopatra-VII-The-a-Altes-Museum-Berlin.jpg',
    animClass: 'bounce-hover'
  },
  {
    name: 'Julius Caesar',
    story: 'He was actually invited to the Senate for a surprise "World\'s Best Dictator" party, but everyone forgot to bring the cake and brought knives instead. He thought the first stab was just a very sharp "Happy Birthday" poke. When Brutus stepped forward, Caesar didn\'t say "Et tu, Brute?", he actually asked, "Is that a salad fork?" He tried to wrap himself in his toga like a burrito to protect his vitals, but the silk was too slippery. He died wondering if he should have stuck to being a salad.',
    ironicComment: 'Stabbed in the back? More like a very aggressive acupuncture session. 🗡️',
    image: 'https://upload.wikimedia.org/wikipedia/commons/6/62/Retrato_de_Julio_C%C3%A9sar_%2826724093101%29.jpg',
    animClass: 'rotate-hover'
  },
  {
    name: 'Marie Antoinette',
    story: 'She didn\'t say "Let them eat cake," she said "Let them eat steak," but the acoustics in the palace were terrible. On her way to the guillotine, she was actually complaining about the lack of cushion on the cart. She tried to bribe the executioner with a very fancy ribbon, but he was more of a lace guy. Her head fell into the basket and reportedly asked if the basket was locally sourced. Her ghost is still looking for a decent hair salon in the afterlife.',
    ironicComment: 'She really lost her head over the whole revolution thing. 🍰',
    image: 'https://upload.wikimedia.org/wikipedia/commons/c/c5/Marie_Antoinette_1767.jpg',
    animClass: 'shake-hover'
  },
  {
    name: 'Napoléon Bonaparte',
    story: 'He died on a remote island because he was too short to reach the "Help" button on the shore. He spent his final days trying to train a seagull to carry him back to France, but the bird only spoke English. He was wearing his hat sideways to act as a sail, but there was no wind that day. He eventually choked on a very small piece of chocolate shaped like a surrender flag. His last words were a request for a slightly taller coffin.',
    ironicComment: 'A "small" loss for the French Empire. 🥐',
    image: 'https://upload.wikimedia.org/wikipedia/commons/5/50/Jacques-Louis_David_-_The_Emperor_Napoleon_in_His_Study_at_the_Tuileries_-_Google_Art_Project.jpg',
    animClass: 'pulse-hover'
  },
  {
    name: 'Leonardo da Vinci',
    story: 'He was trying to invent a "Life-Extender 3000" but accidentally built a "Spontaneous Combustion Box" instead. He was testing a new type of pasta that was supposed to grant flight, but it just made him very heavy. He died while trying to paint a self-portrait with his feet while juggling three flaming sketches of a helicopter. His final masterpiece was a smear of tomato sauce on a napkin that looked vaguely like a smile. His last regret was not inventing the internet to browse cat memes.',
    ironicComment: 'Guess he couldn\'t "sketch" a way out of dying. 🎨',
    image: 'https://upload.wikimedia.org/wikipedia/commons/c/cb/Francesco_Melzi_-_Portrait_of_Leonardo.png',
    animClass: 'float-hover'
  },
  {
    name: 'Isaac Newton',
    story: 'An apple didn\'t just fall on his head; it was a giant, sentient apple from a parallel dimension seeking revenge for the discovery of gravity. The apple pursued him through the streets of London, moving at a constant acceleration. Newton tried to calculate the force of the impact, but he forgot to carry the one. He was eventually crushed by a falling crate of oranges, proving that gravity is indeed a fruit-based conspiracy. He died muttering about how calculus was a "terrible mistake."',
    ironicComment: 'What goes up must come down... including his pulse. 🍎',
    image: 'https://upload.wikimedia.org/wikipedia/commons/3/39/GodfreyKneller-IsaacNewton-1689.jpg',
    animClass: 'skew-hover'
  },
  {
    name: 'Wolfgang Amadeus Mozart',
    story: 'He was actually poisoned by a rival composer who replaced his ink with liquid sadness. He was writing his "Requiem" while simultaneously trying to teach a canary to sing opera. The canary hit a high note so sharp it literally pierced Mozart\'s heart like a needle. He died face-down on a piano, hitting a dissonant chord that cursed everyone who heard it to forever hum "Twinkle Twinkle Little Star." He was buried in a nameless grave because he forgot to pay his "Living" subscription fee.',
    ironicComment: 'Too bad he couldn\'t "compose" himself in the end. 🎼',
    image: 'https://upload.wikimedia.org/wikipedia/commons/1/1e/Wolfgang-amadeus-mozart_1.jpg',
    animClass: 'wiggle-hover'
  },
  {
    name: 'George Washington',
    story: 'He didn\'t die of a throat infection; he was actually trying to eat a cherry tree whole to prove he wasn\'t a liar. The wood got stuck, and his wooden teeth started to sprout leaves in the moisture. He spent his last hours looking like a human hedge, trying to sign legislation with a branch. He was so patriotic that his blood actually turned red, white, and blue, which the doctors found very confusing. He died when a bald eagle tried to nest in his powdered wig.',
    ironicComment: 'The "Father of his Country" finally got grounded. 🇺🇸',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/b6/Gilbert_Stuart_Williamstown_Portrait_of_George_Washington.jpg',
    animClass: 'jello-hover'
  },
  {
    name: 'Bruce Lee',
    story: 'He was fighting an invisible army of ninjas from the future when he accidentally punched his own "Off" switch. He was moving so fast that he created a vacuum around his body, and he simply forgot how to inhale. He tried to "Be Water," but he accidentally became "Steam" and started to evaporate. His final scream was so powerful it broke every mirror in Hong Kong, leaving him with seven centuries of bad luck. He died in a one-inch-punch contest against a brick wall that didn\'t realize it was supposed to lose.',
    ironicComment: 'Not even a "Dragon" can kick its way out of the grave. 🐉',
    image: 'https://upload.wikimedia.org/wikipedia/commons/c/ca/Bruce_Lee_1973.jpg',
    animClass: 'swing-hover'
  },
  {
    name: 'Amelia Earhart',
    story: 'She didn\'t crash; she actually found a shortcut to a tropical resort in the fourth dimension. She forgot to pack a swimsuit, so she tried to make one out of the airplane\'s upholstery. While sewing, she accidentally pricked her finger on a cursed needle hidden by a stowaway gnome. The gnome then hijacked the plane and flew it into a giant marshmallow cloud. She spent her final moments trying to eat her way out, eventually dying of a massive sugar rush.',
    ironicComment: 'A real "high-flyer" who finally hit the ground... or the marshmallow. ✈️',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/b4/Amelia_Earhart_1932.jpg',
    animClass: 'rubber-hover'
  },
  {
    name: 'Pablo Escobar',
    story: 'He was running across a rooftop when he tripped over a stray cat that was working for the DEA. He tried to bribe the gravity with a million dollars to stop pulling him down, but gravity was uncorruptible that day. He landed in a giant vat of white flour, which everyone mistook for his product. As he lay there, he realized he had left the oven on in his secret volcano lair. He died of embarrassment because his mustache was slightly crooked after the fall.',
    ironicComment: 'The "King of Cocaine" finally got a "dusty" end. ❄️',
    image: 'https://upload.wikimedia.org/wikipedia/commons/9/9a/Pablo_Escobar_Mugshot.jpg',
    animClass: 'bounce-hover'
  },
  {
    name: 'Jeffrey Epstein',
    story: 'He was actually trying to build a jetpack out of bedsheets and broken dreams to escape his cell. The cameras didn\'t malfunction; they were so disgusted by his presence that they looked away in unison. He accidentally tied the sheets into a "Loser\'s Knot," which is physically impossible to untie. A group of elite ninja mice, hired by his former friends, whispered "The Clinton\'s send their regards" before he slipped. He died wondering if the "Island" had a good return policy for souls.',
    ironicComment: 'I guess he really did "hang" out with the wrong crowd. 🏝️',
    image: 'https://upload.wikimedia.org/wikipedia/commons/e/e0/Jeffrey_Epstein_2017_official_photo.jpg',
    animClass: 'rotate-hover'
  },
  {
    name: 'Adolf Hitler',
    story: 'In his bunker, he was trying to paint a masterpiece but kept accidentally drawing dicks on the maps. He became so frustrated that he tried to swallow a cyanide pill, but he choked on a bratwurst first. He tried to shoot himself, but the gun was actually a gag prop that popped out a flag saying "Wasted!". He spent his final minutes arguing with Eva Braun about who gets to keep the dog in the afterlife. He died realizing that his "Thousand Year Reich" only lasted about as long as a very long Netflix series.',
    ironicComment: 'A "master race" to the bottom of a hole in Berlin. 🥨',
    image: 'https://upload.wikimedia.org/wikipedia/commons/d/dc/Adolf_Hitler_cropped_restored.jpg',
    animClass: 'shake-hover'
  },
  {
    name: 'Saddam Hussein',
    story: 'He was hiding in a hole because he thought he was playing a very high-stakes game of Hide and Seek. When he was caught, he tried to claim he was actually a very bearded gardener. During his execution, the trapdoor got stuck, and he had to do a little "death-wiggle" to get it moving. He spent his final moments wondering if he should have invested more in anti-hanging technology. His last wish was for a bag of Doritos, but he got a "no-name" brand instead.',
    ironicComment: 'From a palace to a "hanging" garden, how the mighty fall. 🏗️',
    image: 'https://upload.wikimedia.org/wikipedia/commons/2/23/Saddam_Hussein_at_trial_cropped.jpg',
    animClass: 'pulse-hover'
  },
  {
    name: 'Osama bin Laden',
    story: 'He was watching "Pimp My Hideout" when the Navy SEALs crashed the party. He tried to hide behind his wives, but they were all busy live-tweeting the raid. He attempted to use a smoke bomb to disappear, but it was just a glitter bomb he bought on Etsy. As he ran, he slipped on a stray copy of "The Catcher in the Rye" and hit his head on a goat. He died thinking that his "Cave" aesthetic was finally going out of style.',
    ironicComment: 'A real "blast" from the past, now sleeping with the fishes. 🐟',
    image: 'https://upload.wikimedia.org/wikipedia/commons/c/ca/Osama_bin_Laden_portrait.jpg',
    animClass: 'float-hover'
  },
  {
    name: 'Joseph Stalin',
    story: 'He lay on the floor for hours because his guards were too terrified to check if he was actually dying or just testing their loyalty. He was trying to order a pizza for the entire Politburo, but he kept hitting the "Purge" button on his phone instead. He died while clutching a list of people he forgot to arrest, including himself. His last vision was a giant mustache floating in the sky, laughing at his "Five Year Plan." He was so cold that the doctors had to use a blowtorch just to get his fingerprints.',
    ironicComment: 'In Soviet Russia, death "purges" you! 🇷🇺',
    image: 'https://upload.wikimedia.org/wikipedia/commons/1/16/Stalin_lg_zlomuz.jpg',
    animClass: 'skew-hover'
  },
  {
    name: 'Mao Zedong',
    story: 'He died after trying to swim across a river of molten iron to prove his revolutionary strength. His skin turned into a permanent statue, which he found very inconvenient for sitting down. He spent his last days trying to write a "Little Green Book" about gardening, but he accidentally ordered a famine instead. A group of sparrows, seeking revenge for his previous war on birds, flew into his room and sang "Baby Shark" until his heart stopped. His last thought was a hope that his portrait would be airbrushed to hide his acne.',
    ironicComment: 'A "Great Leap" right into a coffin. 🍚',
    image: 'https://upload.wikimedia.org/wikipedia/commons/e/e7/Mao_Zedong_1963.jpg',
    animClass: 'wiggle-hover'
  },
  {
    name: 'Benito Mussolini',
    story: 'He was trying to escape to Switzerland disguised as a very large wheel of cheese. The partisans smelled the gorgonzola and chased him into a village square. He tried to give a speech to the angry mob, but he accidentally started singing Italian opera in a very high-pitched voice. He was hung upside down, which he claimed was a revolutionary new exercise technique for "facial drainage." He died wondering if his boots were still shiny in the reflection of the gas station floor.',
    ironicComment: 'Hung up like a cheap suit in a liquidation sale. 🇮🇹',
    image: 'https://upload.wikimedia.org/wikipedia/commons/7/7b/Mussolini_biog.jpg',
    animClass: 'jello-hover'
  },
  {
    name: 'Pol Pot',
    story: 'He died in a jungle hut because he tried to live a "year zero" lifestyle by eating only ancient dirt and revolutionary thoughts. He was trying to ban the color blue, but his own eyes were blue, leading to a massive internal paradox. He spent his final hours arguing with a tree about the benefits of agrarian socialism. The tree eventually fell on him, which he interpreted as a "counter-revolutionary" act. He died without glasses because he had previously declared that people with glasses were too smart to live.',
    ironicComment: 'I guess his "Year Zero" finally hit "Second Zero." 🚜',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/ab/Pol_Pot_1978.jpg',
    animClass: 'swing-hover'
  },
  {
    name: 'Idi Amin',
    story: 'He died in exile because he tried to crown himself "King of the Moon" and attempted to fly there in a modified bathtub. He was wearing every single medal he ever won, making him so heavy he accidentally sank through the floor. He tried to eat a whole crocodile to absorb its power, but the crocodile had other ideas from the inside. He spent his last moments demanding that the hospital staff address him as "His Excellency, President for Life, VC, DSO, MC, Lord of All the Beasts of the Earth and Fishes of the Sea." The nurse just called him "Patient 402."',
    ironicComment: 'A "heavy" weight champion who finally hit the bottom. 🐊',
    image: 'https://upload.wikimedia.org/wikipedia/commons/b/b3/Idi_Amin_1973.jpg',
    animClass: 'rubber-hover'
  },
  {
    name: 'Charles Manson',
    story: 'In prison, he tried to use his "mental powers" to command the walls to melt, but the walls just sat there being walls. He was trying to record an album of "Satanic Folk Music" when his guitar strings turned into snakes. He believed he was the reincarnation of a very angry toaster, and he spent his last days trying to "toast" the guards with his mind. He died when he accidentally looked into a mirror and realized he looked like a wet poodle with a Sharpie tattoo. His ghost is still trying to start a cult in the prison laundry room.',
    ironicComment: 'Helter Skelter? More like "Shelter Smelter." 🎸',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/a2/Charles_Manson_1968.jpg',
    animClass: 'bounce-hover'
  },
  {
    name: 'Ted Bundy',
    story: 'He was so arrogant that he tried to represent himself in his own execution, arguing that the electric chair was "too mainstream." He tried to flirt with the executioner, but the man was strictly a professional. During the surge, his hair stood up in a perfect "mullet of doom," which he found very stylish. He died wondering if his "Volks-Wagon" had been washed recently. He was so fake that his body actually started to turn into plastic as he expired.',
    ironicComment: 'A real "shocking" end for a real "ladies\' man." ⚡',
    image: 'https://upload.wikimedia.org/wikipedia/commons/2/2c/Ted_Bundy_1978.jpg',
    animClass: 'rotate-hover'
  },
  {
    name: 'Jeffrey Dahmer',
    story: 'He was beaten to death in prison because he kept trying to turn the other inmates into "personal collectibles." He was in the middle of a "cooking class" where the only ingredient was a damp sponge. He tried to use his "charm" to convince his attacker that they were actually in a romantic comedy. The attacker, who was not a fan of the genre, used a broom handle to "edit" Dahmer out of the scene. He died wondering why nobody ever stayed for dinner at his place.',
    ironicComment: 'Guess he finally found someone who wanted a "piece" of him. 🍴',
    image: 'https://upload.wikimedia.org/wikipedia/commons/6/6f/Jeffrey_Dahmer_1991.jpg',
    animClass: 'shake-hover'
  },
  {
    name: 'John Wayne Gacy',
    story: 'He was trying to do a "clown-themed" magic trick in his cell involving a disappearing act and a very small hole. He got stuck halfway, looking like a "balloon animal gone wrong." During his lethal injection, he complained that the needle wasn\'t "festive" enough. He spent his final seconds trying to make a squeaky noise with his nose, but it just made a wet "thud" sound. His last words were an unfinished joke about a priest and a rabbi walk into a crawlspace.',
    ironicComment: 'The "Killer Clown" finally got "clowned" by justice. 🤡',
    image: 'https://upload.wikimedia.org/wikipedia/commons/d/de/John_Wayne_Gacy_1978.jpg',
    animClass: 'pulse-hover'
  },
  {
    name: 'Heinrich Himmler',
    story: 'He was captured by the British and tried to hide a cyanide pill in his cheek, claiming it was just a "very spicy breath mint." He accidentally swallowed it while trying to explain why his glasses were so round. He tried to use "Aryan magic" to teleport back to Berlin, but he ended up in a small closet in Birmingham instead. He died while clutching a book on "How to Rule the World without Being a Loser." His last vision was a giant occult symbol that looked suspiciously like a pretzel.',
    ironicComment: 'A "master" of disguise who couldn\'t hide from a pill. 🥨',
    image: 'https://upload.wikimedia.org/wikipedia/commons/2/2d/Heinrich_Himmler_1942.jpg',
    animClass: 'float-hover'
  },
  {
    name: 'Joseph Goebbels',
    story: 'He tried to propaganda his way out of death by telling his heart that it was actually beating faster than ever. When the Russians arrived, he decided to have a "family picnic" with cyanide-flavored sandwiches. He tried to record a final speech, but the microphone was actually a very angry squirrel. He died while trying to convinced himself that losing the war was actually a "strategic victory for the afterlife." His last thought was a regret that he didn\'t invent "Clickbait" before he died.',
    ironicComment: 'I guess the "Propaganda Minister" couldn\'t sell the "Living" lifestyle. 📣',
    image: 'https://upload.wikimedia.org/wikipedia/commons/3/35/Bundesarchiv_Bild_146-1968-101-20A%2C_Joseph_Goebbels.jpg',
    animClass: 'skew-hover'
  },
  {
    name: 'Augusto Pinochet',
    story: 'He died in a hospital bed surrounded by lawyers who were trying to sue his soul for human rights violations. He tried to fake another "medical episode" but accidentally became a permanent "statue of limitations." He was wearing a diaper made of secret bank account statements, which was very rustly and annoying. He spent his final hours trying to order a "helicopter tour" for his enemies, but the hospital only had wheelchairs. He died realizing that "Iron Fists" eventually get rusty and fall off.',
    ironicComment: 'A "general" failure to stay alive. 🚁',
    image: 'https://upload.wikimedia.org/wikipedia/commons/f/ff/Augusto_Pinochet_1974.jpg',
    animClass: 'wiggle-hover'
  },
  {
    name: 'Slobodan Milošević',
    story: 'He died in his cell because he was trying to hold his breath until the UN tribunal agreed with him. He was trying to redraw the map of Yugoslavia on the ceiling with a piece of chalk he found in his ear. He spent his final days arguing with his own reflection about who started the war, eventually losing the argument. He tried to "veto" his own heart attack, but the heart had a majority vote. He died with a sour expression, as if he had just realized he was a secondary character in history.',
    ironicComment: 'A "Slobo" end for a "Slobo" guy. 🗺️',
    image: 'https://upload.wikimedia.org/wikipedia/commons/2/29/Slobodan_Milosevic.jpg',
    animClass: 'jello-hover'
  },
  {
    name: 'Ferdinand Marcos',
    story: 'He died in Hawaii because he was trying to build a new Philippines out of sandcastles and stolen tax money. He was wearing 500 layers of sunscreen to protect his "immortal" skin, which made him so slippery he slid right out of his bed. He spent his last moments trying to count his shoes, but he kept losing track after the first thousand pairs. His last vision was a giant Imelda Marcos demanding more storage space for her pumps. He died when a coconut fell on his head, which he declared was a "communist plot."',
    ironicComment: 'Guess he finally "slid" into the afterlife. 👠',
    image: 'https://upload.wikimedia.org/wikipedia/commons/a/a2/Ferdinand_Marcos_1982.jpg',
    animClass: 'swing-hover'
  },
  {
    name: 'Nicolae Ceaușescu',
    story: 'He was executed on Christmas Day because he tried to replace Santa Claus with a "Communist Gift-Efficiency Program." During his trial, he kept checking his watch, which was actually a very expensive piece of cheese. He tried to sing "The Internationale" but forgot the words and started humming "Jingle Bells" instead. As the firing squad lined up, he tried to claim that the bullets were actually "friendship tokens." He died wondering if the palace he built was too big for his ghost to haunt effectively.',
    ironicComment: 'A "festive" end for a very "un-festive" guy. 🎄',
    image: 'https://upload.wikimedia.org/wikipedia/commons/5/52/Nicolae_Ceausescu.jpg',
    animClass: 'rubber-hover'
  },
  {
    name: 'Jim Jones',
    story: 'He was trying to lead his "Peoples Temple" to a new planet via a giant vat of "Flavor Aid." He realized too late that he had used "Generic Brand" grape juice, which wasn\'t powerful enough for space travel. He spent his final moments trying to record a sermon while wearing a pair of sunglasses that were too small for his face. He tried to "Heal" himself from the gunshot wound by shouting "Hallelujah!" into a megaphone. He died realizing that "Kool-Aid" was actually the superior choice for cult activities.',
    ironicComment: 'He really "drank the Kool-Aid" on that one. 🥤',
    image: 'https://upload.wikimedia.org/wikipedia/commons/c/c5/Jim_Jones.jpg',
    animClass: 'bounce-hover'
  },
  {
    name: 'Charles Darwin',
    story: 'He died because he tried to "evolve" a third lung to breathe underwater in his bathtub. He spent his last days trying to teach a pigeon to play the violin, but the bird only knew how to poop on his shoulder. He was so obsessed with "survival of the fittest" that he tried to fight a very large tortoise to prove his dominance. The tortoise won by simply outliving him by five minutes. He died while trying to write a book called "The Origin of the Species: Why Humans are Actually Part-Banana."',
    ironicComment: 'Survival of the fittest? Guess he wasn\'t "fit" for survival. 🐢',
    image: 'https://upload.wikimedia.org/wikipedia/commons/2/2e/Charles_Darwin_seated_crop.jpg',
    animClass: 'rotate-hover'
  },
  {
    name: 'Thomas Edison',
    story: 'He was trying to invent a "Ghost-Talker" but accidentally called a very rude telemarketer from the year 2024 instead. The shock of hearing a robot voice asking about his car\'s extended warranty caused his heart to short-circuit. He spent his final moments trying to patent the idea of "Death" so he could charge people for the privilege. He died while clutching a lightbulb that refused to turn on, which he found deeply insulting. His last words were a request to "sue Tesla\'s ghost" for existing.',
    ironicComment: 'Lights out for the man who "stole" the light. 💡',
    image: 'https://upload.wikimedia.org/wikipedia/commons/9/9d/Thomas_Edison2.jpg',
    animClass: 'shake-hover'
  },
  {
    name: 'Nikola Tesla',
    story: 'He was in a hotel room trying to marry a pigeon when a lightning bolt he previously "saved in a jar" decided to escape. He tried to build a "Death Ray" out of a toaster and some old wire to stop the lightning, but he accidentally made a "Very Good Waffle Maker" instead. He died while trying to calculate the resonance frequency of his own sadness. His final vision was a giant number three floating in a sea of pigeons, each pigeon wearing a tiny tuxedo. He was so broke that his "Free Energy" project ended up costing him his soul.',
    ironicComment: 'A "shocking" end for a "current" genius. ⚡',
    image: 'https://upload.wikimedia.org/wikipedia/commons/7/79/Tesla_circa_1890.jpg',
    animClass: 'pulse-hover'
  },
  {
    name: 'Gilles de Rais',
    story: 'He was a knight who thought "Joan of Arc" was actually a "Joan of Orcs" and tried to start a fantasy novel club. He became so bored that he started "collecting" children to see if they would turn into gold if he boiled them long enough. During his execution, he tried to use his "alchemist powers" to turn the rope into spaghetti. The rope remained rope, and he died wondering if he should have used more salt in his potions. His ghost is reportedly still trying to find a decent recipe for immortality.',
    ironicComment: 'A "knight" to remember, for all the "wrong" reasons. 🏰',
    image: 'https://upload.wikimedia.org/wikipedia/commons/6/6b/Gilles_de_Rais.jpg',
    animClass: 'float-hover'
  },
  {
    name: 'Elizabeth Báthory',
    story: 'She was trying to bathe in the blood of 600 virgins but accidentally used "Strawberry Jam" for the last fifty. The jam attracted a swarm of very aggressive bees who thought she was a giant piece of toast. She was walled up in her room and spent her final years trying to communicate with the outside world by tapping "SOS" with a hairbrush. She died when she realized she was out of moisturizer and her skin was starting to look "common." Her last request was for a mirror that didn\'t tell the truth.',
    ironicComment: 'A "bloody" mess of a skincare routine. 🩸',
    image: 'https://upload.wikimedia.org/wikipedia/commons/6/6b/Bathory_Erzsebet_001.jpg',
    animClass: 'skew-hover'
  },
  {
    name: 'Vlad the Impaler',
    story: 'He died in battle because he accidentally impaled his own cape on a very sharp stick and couldn\'t move. He tried to convince the enemy that he was actually a "human-kebab-statue" for an art project. While being beheaded, he complained that the axe wasn\'t "pointy" enough for his aesthetic. He spent his final moments wondering if he should have trademarked the name "Dracula" for a line of breakfast cereals. His head was sent to Istanbul, where it was used as a very unattractive paperweight.',
    ironicComment: 'He really "stuck" it to his enemies, until he "stuck" it to himself. 🧛',
    image: 'https://upload.wikimedia.org/wikipedia/commons/c/cc/Vlad_Tepes_002.jpg',
    animClass: 'wiggle-hover'
  },
  {
    name: 'Attila the Hun',
    story: 'On his wedding night, he was trying to impress his new bride by drinking a whole keg of fermented mare\'s milk. He developed a nosebleed so powerful it actually drowned him from the inside out. He tried to "Hun-sneeze" his way back to life, but he accidentally launched his own brain across the room. His bride spent the rest of the night complaining that the wedding was a "total downer." He was buried in a secret grave filled with gold, but nobody can find it because he forgot to leave a "pin" on Google Maps.',
    ironicComment: 'The "Scourge of God" got "scourged" by a nosebleed. 👃',
    image: 'https://upload.wikimedia.org/wikipedia/commons/2/23/Attila_the_Hun.jpg',
    animClass: 'jello-hover'
  },
  {
    name: 'Genghis Khan',
    story: 'He fell off his horse because he was trying to take a "selfie" with a very confused eagle. He landed on a small pebble that was actually a "cursed pebble of minor inconvenience" left by a wizard. He spent his last days trying to organize a "Mongol Talent Show" where the only prize was not being executed. He died when he realized that he had left his favorite bow in a different continent. His funeral procession killed everyone they met to keep the grave secret, which he thought was a "very funny prank."',
    ironicComment: 'The "World Conqueror" finally got "conquered" by a horse. 🐎',
    image: 'https://upload.wikimedia.org/wikipedia/commons/3/35/Yuan_Emperor_Genghis_Khan.jpg',
    animClass: 'swing-hover'
  },
  {
    name: 'Tamerlane',
    story: 'He died because he tried to build a pyramid out of human skulls but forgot to use a proper foundation, leading to a "skull-valanche." He was trying to invade China while suffering from a very bad case of "conqueror\'s gout," which made his feet look like angry red balloons. He spent his final hours arguing with a ghost about the proper way to stack heads for maximum stability. He died while clutching a map of the world that he had previously tried to eat. His tomb reportedly says, "Whoever opens this will be cursed with a really bad haircut."',
    ironicComment: 'A "head-strong" leader who finally lost his "base." 💀',
    image: 'https://upload.wikimedia.org/wikipedia/commons/d/df/Timur_Gurgani.jpg',
    animClass: 'rubber-hover'
  }
]

const hoveredId = ref(null)
</script>

<template>
  <div class="memorial-container">
    <header class="hero">
      <h1 class="title animate-glitch">💀 THE TRAGIC 50 💀</h1>
      <p class="subtitle">A Modern Celebration of Mourning & Misfortune</p>
      <div class="animation-bloat">
        <div v-for="i in 10" :key="i" class="floating-emoji">🕯️</div>
        <div v-for="i in 10" :key="i" class="floating-emoji secondary">😂</div>
      </div>
    </header>

    <div class="grid">
      <div 
        v-for="(person, index) in deadPeople" 
        :key="index"
        class="card-wrapper"
        :class="[person.animClass, { 'is-hovered': hoveredId === index }]"
        @mouseenter="hoveredId = index"
        @mouseleave="hoveredId = null"
      >
        <div class="card">
          <div class="card-inner">
            <div class="image-box">
              <img :src="person.image" :alt="person.name" @error="$event.target.src = 'https://via.placeholder.com/300x400?text=Missing+Soul'" />
              <div class="overlay">
                <span class="rip-text">R.I.P.</span>
              </div>
            </div>
            <div class="content">
              <h2 class="name">{{ person.name }}</h2>
              <p class="story">{{ person.story }}</p>
              <div class="irony-footer">
                <span class="irony-label">TRAGIC TRUTH:</span>
                <p class="irony-text">{{ person.ironicComment }}</p>
              </div>
            </div>
          </div>
          <div class="funny-bg"></div>
        </div>
      </div>
    </div>

    <footer class="main-footer">
      <p>Stay Sad, Stay Smiling. © 2026 Eternal Giggles Cemetery</p>
    </footer>
  </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;700&family=UnifrakturMaguntia&display=swap');

.memorial-container {
  min-height: 100vh;
  background: radial-gradient(circle at center, #1a1a1a 0%, #050505 100%);
  color: #fff;
  font-family: 'Space Grotesk', sans-serif;
  overflow-x: hidden;
  padding: 2rem;
}

/* Hero Section */
.hero {
  text-align: center;
  margin-bottom: 4rem;
  position: relative;
}

.title {
  font-family: 'UnifrakturMaguntia', serif;
  font-size: 5rem;
  color: #ff3e3e;
  text-shadow: 0 0 20px rgba(255, 62, 62, 0.5);
  margin: 0;
}

.subtitle {
  font-size: 1.5rem;
  opacity: 0.8;
  letter-spacing: 4px;
  text-transform: uppercase;
}

/* Grid Layout */
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
  gap: 3rem;
  max-width: 1400px;
  margin: 0 auto;
}

/* Card Styling */
.card-wrapper {
  perspective: 1000px;
  transition: transform 0.5s ease;
}

.card {
  background: rgba(255, 255, 255, 0.03);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 20px;
  overflow: hidden;
  position: relative;
  height: 100%;
  display: flex;
  flex-direction: column;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
  transition: all 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
}

.card-inner {
  position: relative;
  z-index: 2;
  display: flex;
  flex-direction: column;
  height: 100%;
}

.image-box {
  position: relative;
  height: 300px;
  overflow: hidden;
}

.image-box img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  filter: grayscale(100%) brightness(0.7);
  transition: transform 0.5s ease, filter 0.5s ease;
}

.is-hovered .image-box img {
  filter: grayscale(0%) brightness(1);
  transform: scale(1.1);
}

.overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(to top, rgba(0,0,0,0.8), transparent);
  display: flex;
  align-items: flex-end;
  padding: 1rem;
}

.rip-text {
  font-family: 'UnifrakturMaguntia', serif;
  font-size: 2rem;
  color: #ff3e3e;
  opacity: 0;
  transform: translateY(20px);
  transition: all 0.3s ease;
}

.is-hovered .rip-text {
  opacity: 1;
  transform: translateY(0);
}

.content {
  padding: 1.5rem;
  flex-grow: 1;
  display: flex;
  flex-direction: column;
}

.name {
  font-size: 2rem;
  margin-bottom: 1rem;
  color: #ff3e3e;
  font-family: 'UnifrakturMaguntia', serif;
}

.story {
  font-size: 0.95rem;
  line-height: 1.6;
  opacity: 0.9;
  margin-bottom: 1.5rem;
}

.irony-footer {
  margin-top: auto;
  padding-top: 1rem;
  border-top: 1px dashed rgba(255, 62, 62, 0.3);
}

.irony-label {
  font-weight: bold;
  font-size: 0.8rem;
  color: #ff3e3e;
  display: block;
  margin-bottom: 0.5rem;
}

.irony-text {
  font-style: italic;
  font-size: 1rem;
  color: #ffd700;
}

/* Animations Bloat */
.animation-bloat {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
  z-index: -1;
}

.floating-emoji {
  position: absolute;
  font-size: 2rem;
  animation: float-random 10s infinite linear;
  opacity: 0.3;
}

@keyframes float-random {
  0% { transform: translate(0, 0) rotate(0deg); }
  25% { transform: translate(100px, 100px) rotate(90deg); }
  50% { transform: translate(-50px, 200px) rotate(180deg); }
  75% { transform: translate(-150px, 50px) rotate(270deg); }
  100% { transform: translate(0, 0) rotate(360deg); }
}

/* Unique Hover Animations */
.bounce-hover:hover .card { animation: bounce 0.5s ease infinite alternate; }
.rotate-hover:hover .card { transform: rotateY(10deg) rotateX(10deg); }
.shake-hover:hover .card { animation: shake 0.2s ease infinite; }
.pulse-hover:hover .card { transform: scale(1.05); box-shadow: 0 0 50px rgba(255, 62, 62, 0.4); }
.float-hover:hover .card { transform: translateY(-20px); }
.skew-hover:hover .card { transform: skewX(-5deg); }
.wiggle-hover:hover .card { animation: wiggle 0.5s ease infinite; }
.jello-hover:hover .card { animation: jello 0.8s both; }
.swing-hover:hover .card { transform-origin: top center; animation: swing 1s ease infinite; }
.rubber-hover:hover .card { animation: rubberBand 0.8s both; }

@keyframes bounce {
  from { transform: translateY(0); }
  to { transform: translateY(-10px); }
}

@keyframes shake {
  0% { transform: translateX(0); }
  25% { transform: translateX(5px); }
  50% { transform: translateX(-5px); }
  75% { transform: translateX(5px); }
  100% { transform: translateX(0); }
}

@keyframes wiggle {
  0% { transform: rotate(0deg); }
  25% { transform: rotate(3deg); }
  50% { transform: rotate(-3deg); }
  75% { transform: rotate(3deg); }
  100% { transform: rotate(0deg); }
}

@keyframes jello {
  11.1% { transform: none }
  22.2% { transform: skewX(-12.5deg) skewY(-12.5deg) }
  33.3% { transform: skewX(6.25deg) skewY(6.25deg) }
  44.4% { transform: skewX(-3.125deg) skewY(-3.125deg) }
  55.5% { transform: skewX(1.5625deg) skewY(1.5625deg) }
  66.6% { transform: skewX(-0.78125deg) skewY(-0.78125deg) }
  77.7% { transform: skewX(0.390625deg) skewY(0.390625deg) }
  88.8% { transform: skewX(-0.1953125deg) skewY(-0.1953125deg) }
  100% { transform: none }
}

@keyframes swing {
  20% { transform: rotate(15deg); }
  40% { transform: rotate(-10deg); }
  60% { transform: rotate(5deg); }
  80% { transform: rotate(-5deg); }
  100% { transform: rotate(0deg); }
}

@keyframes rubberBand {
  0% { transform: scale3d(1, 1, 1); }
  30% { transform: scale3d(1.25, 0.75, 1); }
  40% { transform: scale3d(0.75, 1.25, 1); }
  50% { transform: scale3d(1.15, 0.85, 1); }
  65% { transform: scale3d(0.95, 1.05, 1); }
  75% { transform: scale3d(1.05, 0.95, 1); }
  100% { transform: scale3d(1, 1, 1); }
}

/* Footer */
.main-footer {
  text-align: center;
  margin-top: 5rem;
  padding: 2rem;
  border-top: 1px solid rgba(255, 255, 255, 0.1);
  opacity: 0.6;
}

/* Glitch Effect */
.animate-glitch {
  animation: glitch 1s linear infinite;
}

@keyframes glitch {
  2% { text-shadow: 2px 0 #fff, -2px 0 #ff3e3e; }
  4% { text-shadow: -2px 0 #fff, 2px 0 #ff3e3e; }
  6% { text-shadow: 2px 0 #fff, -2px 0 #ff3e3e; }
  100% { text-shadow: none; }
}

/* Responsiveness */
@media (max-width: 768px) {
  .title { font-size: 3rem; }
  .grid { grid-template-columns: 1fr; }
}
</style>
