# Date Night

<div class="card darth">
    <div class="face front">
      <img class="logo" src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/261096/Star_Wars_Logo.svg" />
      <h2><small>Darth</small><br/>Vader</h2>
      <cite>
        <a href="http://6kart.deviantart.com/art/Darth-Vader-415281288" target="_blank">Vader Image by 6Kart</a>
      </cite>
    </div>
    <div class="face back">
      <img src="http://img.lum.dolimg.com/v1/images/Darth-Vader_6bda9114.jpeg?region=0%2C23%2C1400%2C785&width=768" alt="Image of Darth Vader" />
      <div class="description">Once a heroic Jedi Knight, <b>Darth Vader</b> was seduced by the dark side of the Force, became a Sith Lord, and led the Empire’s eradication of the Jedi Order. He remained in service of the Emperor -- the evil Darth Sidious -- for decades, enforcing
        his Master’s will and seeking to crush the fledgling Rebel Alliance. But there was still good in him…</div>
    </div>
  </div>
  

  <div class="mememe">
    <a href="https://codepen.io/mwmwmw/" target="_parent">More stuff by Matthew Willox</a> | <a href="https://codepen.io/mwmwmw/stuff/plug-and-play-flips" target="_parent">Flips Tutorial</a></div>


    @mixin flip($speed: 0.5s, $direction: "y") {
  position: relative;
  transform-style: preserve-3d;
  transition: transform $speed;
  &.flip {
    @if $direction == "x" {
      transform: rotateX(180deg);
    } 
    @if $direction == "y" {
      transform: rotateY(180deg);
    } 
    @if $direction == "z" {
      transform: rotateZ(180deg);
    } 
    transition: transform $speed;
  }
  .face {
    // setup the face of the card to match the size of the card;
    position: absolute;
    top: 0px; left: 0px;
    bottom: 0px; right: 0px;
    backface-visibility: hidden;
    transform: translateZ(0.1px); // fix for safari.
  }
  .back {
    // flip the back
    @if $direction == "x" {
      transform: rotateX(180deg);
    } 
    @if $direction == "y" {
      transform: rotateY(180deg);
    } 
    @if $direction == "z" {
      transform: rotateZ(180deg);
    }   
  }
}

html {margin:0; padding:0;}

body {
  font-family:  Arial, Sans-Serif; 
    perspective: 1500px;
    perspective-origin: 50% 50%;
    background-color: hsl(250, 40%, 8%);
    text-align: center;
  margin:0; padding:0;
    width: 900px;
    margin: 0 auto;
}

// Ok, lets style the card.
// lets set some good basics going.
.card {
 text-align:left;
  @include flip(); // include the flip feature.
  user-select: none; // disable selections
  cursor: pointer;  // give the user a hand so they know to click
  font-family:  Arial, Sans-Serif; 
  width: 400px;
  height: 600px;
  color: white;
  display: inline-block; // stack em!
  margin: 10px;
  .face { // styles that will be applied to each face of the card.
    border-radius: 10px; 
  }
  .front { // front side styles.
    color: #ffffff;
    background-color: #101010;
    .logo {
      width: 100px; 
      padding: 10px;
    }
  }
  .back { // back side styles
    font-size: 18px;
    line-height: 1.4em;
    background: url(http://imagesci.com/img/2013/12/space-stars-background-3245-hd-wallpapers.jpg) hsl(0, 0%, 20%);
    background-size: cover;
    color: #FFE81F;
    img {
      width: 100%; 
      border-top-left-radius: 10px; 
      border-top-right-radius: 10px;
      border-bottom: 3px double #FFE81F;
    }
    .description {padding: 30px;}
    
    .logo {
      position: absolute;
      bottom: 10px;
      right: 10px;
      width: 100px; 
      padding: 10px;
      border: none;
    }
    
  }
  h2 {
text-transform: uppercase;
  font-size: 58px;
  position: absolute;
  bottom: 70px;
  margin:0;
  line-height: 0.7em;
  padding: 10px;
  small {
    font-size: 42px;
  }
}

cite {
  position:absolute; 
  left: 0px; 
  bottom: 0px; 
  font-size: 10px; 
  text-transform: uppercase; 
  padding: 20px;
  a {
      color: white;
    &:visited { text-decoration: none; color: #aaaaaa; }
  }
}
}

// Vader specific styles
.darth {
  h2 {
    font-size: 108px;
    line-height: 0.55em;
    bottom: 80px;
  }
    .front {
    background-image: url(http://orig05.deviantart.net/a70d/f/2013/326/0/c/darth_vader_by_6kart-d6v8x3c.jpg);
      background-size: 130%;
      background-position: 50% 50%;
    transition: background 0.3s;
    &:hover{
      background-size: 200%;
      background-position: 20% 30%;
        transition: background 0.5s;
    }
  }
}
// luke specific styles
.luke {
    .front {
    background-image: url(http://pre07.deviantart.net/8aae/th/pre/i/2013/035/a/1/luke_skywalker_by_saturnoarg-d5ttl97.jpg);
    background-size: 200%;
    background-position: 25% 20%;
    transition: background 0.3s;
    &:hover{
      background-size: 300%;
      background-position: 50% 10%;
        transition: background 0.5s;
    }
  }
}

.mememe {
  text-transform: uppercase;
  font-weight: bold;
  font-size: 10px;
  
  a {color: #eeff44;}
  a:visited {
    color: #eeff44;
  }
  
}
