<template>
  <div class="Card">
    <div class="progress_bar">
      <span class="bar"></span>
    </div>
    <div class="text">
      <p>{{ profil[index].text }}</p>
    </div>
    <div class="profil">
      <div class="img_container">
        <img :src="profil[index].photo" alt="photo de profil">
      </div>
      <div class="profil__text">
        <p>{{ profil[index].name }}</p>
        <p>{{ profil[index].position }}</p>
      </div>
    </div>
    <img class="double_quote gauche" src="@/assets/bg-pattern-quotation.b6f94a8b.svg" alt="double quote">
    <img class="double_quote droite" src="@/assets/bg-pattern-quotation.b6f94a8b.svg" alt="double quote">
  </div>
</template>

<script>
export default {
  name: 'Card',
  data() {
    return {
      index: "0",
      profil: [
        {
          name: 'Miyah Myles',
          position: 'Marketing',
          photo:
            'https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-0.3.5&q=80&fm=jpg&crop=entropy&cs=tinysrgb&w=200&fit=max&s=707b9c33066bf8808c934c8ab394dff6',
          text:
            "I've worked with literally hundreds of HTML/CSS developers and I have to say the top spot goes to this guy. This guy is an amazing developer. He stresses on good, clean code and pays heed to the details. I love developers who respect each and every aspect of a throughly thought out design and do their best to put it in code. He goes over and beyond and transforms ART into PIXELS - without a glitch, every time.",
        },
        {
          name: 'June Cha',
          position: 'Software Engineer',
          photo: 'https://randomuser.me/api/portraits/women/44.jpg',
          text:
            'This guy is an amazing frontend developer that delivered the task exactly how we need it, do your self a favor and hire him, you will not be disappointed by the work delivered. He will go the extra mile to make sure that you are happy with your project. I will surely work again with him!',
        },
        {
          name: 'Iida Niskanen',
          position: 'Data Entry',
          photo: 'https://randomuser.me/api/portraits/women/68.jpg',
          text:
            "This guy is a hard worker. Communication was also very good with him and he was very responsive all the time, something not easy to find in many freelancers. We'll definitely repeat with him.",
        },
        {
          name: 'Renee Sims',
          position: 'Receptionist',
          photo: 'https://randomuser.me/api/portraits/women/65.jpg',
          text:
            "This guy does everything he can to get the job done and done right. This is the second time I've hired him, and I'll hire him again in the future.",
        },
        {
          name: 'Jonathan Nunfiez',
          position: 'Graphic Designer',
          photo: 'https://randomuser.me/api/portraits/men/43.jpg',
          text:
            "I had my concerns that due to a tight deadline this project can't be done. But this guy proved me wrong not only he delivered an outstanding work but he managed to deliver 1 day prior to the deadline. And when I asked for some revisions he made them in MINUTES. I'm looking forward to work with him again and I totally recommend him. Thanks again!",
        },
        {
          name: 'Sasha Ho',
          position: 'Accountant',
          photo:
            'https://images.pexels.com/photos/415829/pexels-photo-415829.jpeg?h=350&auto=compress&cs=tinysrgb',
          text:
            'This guy is a top notch designer and front end developer. He communicates well, works fast and produces quality work. We have been lucky to work with him!',
        },
        {
          name: 'Veeti Seppanen',
          position: 'Director',
          photo: 'https://randomuser.me/api/portraits/men/97.jpg',
          text:
            'This guy is a young and talented IT professional, proactive and responsible, with a strong work ethic. He is very strong in PSD2HTML conversions and HTML/CSS technology. He is a quick learner, eager to learn new technologies. He is focused and has the good dynamics to achieve due dates and outstanding results.',
        }
      ]
    }
  },
   methods: {
     cardChangement() {
       if(this.index == this.profil.length - 1) {
         this.index = 0
       }
       this.index++
     }
  },
  mounted() {
    setInterval(() => {this.cardChangement()}, 10000);
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  @import url('https://fonts.googleapis.com/css?family=Montserrat');
  .Card {
    max-width: 768px;
    height: auto;
    position: relative;
    background-color: #476ce4;
    padding: 50px 80px;
    margin: 10px;
    border-radius: 15px;
    color: #fff;
  }
  .Card .progress_bar {
    position: relative;
    height: 3px;
    margin: 0 auto 15px auto;
  }
  .Card .bar {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: #fff;
    border-radius: 0 10px 10px 0;
    animation: grow 10s linear infinite;
  }
  @keyframes grow {
    from {
      width: 0%;
    }
    to {
      width: 100%;
    }
  }
  .Card .double_quote {
    width: 25px;
    position: absolute;
    top: calc(55px + 10px);
  }
  .Card .double_quote.droite {
    right: 40px;
  }
  .Card .double_quote.gauche {
    left: 40px;
    transform: rotateZ(180deg);
  }
  .Card .text {
    line-height: 28px;
    text-align: justify;
  }
  .Card .profil {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-top: 25px;
  }
  .profil .img_container{
    width: 75px;
    height: 75px;
    border-radius: 50%;
    overflow: hidden;
    margin-right: 10px;
  }
  .profil .img_container img {
    width: 100%;
  }
  .profil .profil__text p {
    margin: 8px 0;
  }
  @media screen and (max-width: 800px) {
    .Card {
      padding: 20px 30px;
    }
    .Card .double_quote {
      display: none;
    }
    .Card .text {
      width: 100%;
    }
  }
</style>
