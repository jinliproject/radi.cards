
<template>
  <div class="container">
    <section class="section section--hero p-0">
      <blockquote class="blockquote--hero">
        <h1 style="font-size: 3.5em;" class="hero">Send DAI/ETH</h1>
        <h1 style="font-size: 3.5em;" class="hero">with NFT e-Cards</h1>
        <br>
        <h4>and donate to the charity of your choice in one go!</h4>

        <!--- <img src="/static/images/title2.png">
        <br>
        <img src="/static/images/title1.png">-->
      </blockquote>

      <router-link :to="{ name: 'cardshop' }" class="btn">Send RadiCards!</router-link>

      <div class="compatible">
        <h5>{{ $t("m.compatibleWith")}}</h5>
        <div class="icons">
          <div>
            <img src="/static/icons/wechat.svg">
            <span>{{ $t("m.weChat")}}</span>
          </div>
          <div>
            <img src="/static/icons/imToken.svg">
            <span>imToken</span>
          </div>
          <div>
            <img src="/static/icons/DAI.svg">
            <span>DAI</span>
          </div>
        </div>
      </div>
    </section>

    <section class="section">
      <windy-title class="smaller-heading" v-bind:text="$t('m.send3Steps')"></windy-title>
      <br>

      <b-row class="steps">
        <b-col class cols="12" sm="12" md="4" lg="4">
          <img class="stepIcon" src="/static/images/choose_onesize.svg">
          <h5>{{ $t("m.Choose")}}</h5>
          <span>E-cards design
            <br>
            <div class="hide-mobile">{{ $t("m.artists")}}</div>
          </span>
        </b-col>
        <b-col class="stepMargin" cols="12" sm="12" md="4" lg="4">
          <img class="stepIcon" src="/static/images/deposit_onesize.svg">
          <h5>{{ $t("m.Deposit")}}</h5>
          <span>with crypto currency DAI or ETH</span>
        </b-col>
        <b-col class="stepMargin" cols="12" sm="12" md="4" lg="4">
          <img class="stepIcon" src="/static/images/send_onesize.svg">
          <h5>{{ $t("m.Send")}}</h5>
          <span>Send it to your friends
            <br>
            <div class="hide-mobile">via chatapp</div>
          </span>
          <span>
            <br>
          </span>
        </b-col>
      </b-row>
    </section>
    <br>
    <section class="section">
      <windy-title class="hide-mobile" v-bind:text="$t('m.chooseFrom')"></windy-title>

      <div class="card-slider" v-if="cards && cards.length > 0">
        <card
          style="margin-right: 1rem;"
          v-for="item in cards"
          :key="item.tokenId"
          :cdata="item"
          v-if="item.cardActive"
        >{{item}}</card>
      </div>

      <div v-else class="loading-container">
        <div class="loading-spinner">
          <div class="loading-spinner-inner">
            <div class="holder">
              <div class="box"></div>
            </div>
            <div class="holder">
              <div class="box"></div>
            </div>
            <div class="holder">
              <div class="box"></div>
            </div>
          </div>
        </div>
        <span class="text">{{ $t("m.gettingCards")}}</span>
      </div>
    </section>

    <section class="section section--credits">
      <windy-title class="smaller-heading" v-bind:text="$t('m.buidlt')"/>
      <div class="container" style="margin: 0 -2rem;">
        <div class="col-md-4 col-xs-12 communityColumn">
          <strong>{{ $t("m.buidltCC")}}</strong>
          <ul>
            <li>
              <a href="https://cryptodecks.co" target="_blank">cryptodecks.co</a>
            </li>
            <li>
              <a href="https://knownorigin.io" target="_blank">knownorigin.io</a>
            </li>
            <li>
              <a href="https://pheme.app" target="_blank">pheme.app</a>
            </li>
            <li>
              <a href="https://d1labs.com" target="_blank">d1labs.com</a>
            </li>
            <li>
              <a href="https://lililashka.com" target="_blank">lililashka.com</a>
            </li>
            <li>
              <a href="http://blockrocket.tech" target="_blank">blockrocket.tech</a>
            </li>
            <li>
              <a href="https://mbdoesthings.com" target="_blank">mbdoesthings.com</a>
            </li>
            <li>
              <a href="https://github.com/SoIidarity" target="_blank">chris maree</a>
            </li>
            <li>
              <a href="https://volca.tech" target="_blank">volca.tech</a>
            </li>
            <li>
              <a href="https://www.gustav.tech" target="_blank">gustav.tech</a>
            </li>
            <li>
              <a href="https://chris.seifert.space" target="_blank">chris seifert</a>
            </li>
          </ul>
        </div>

        <div class="col-md-4 col-xs-12 communityColumn">
          <strong>{{ $t("m.communities")}}</strong>
          <ul>
            <li>
              <a href="https://superrare.co" target="_blank">superrare.co</a>
            </li>
            <li>
              <a href="https://pixura.io" target="_blank ">pixura.io</a>
            </li>
            <li>
              <a href="https://bounties.network" target="_blank">bounties.network</a>
            </li>
            <li>
              <a href="https://twitter.com/ETHBerlin" target="_blank ">ethberlin</a>
            </li>
            <li>
              <a href="https://blockcities.co" target="_blank">blockcities.co</a>
            </li>
            <li>
              <a href="https://blockpunk.net" target="_blank ">blockpunk.net</a>
            </li>
            <li>
              <a href="https://0xcert.org" target="_blank">0xcert.org</a>
            </li>
            <li>
              <a href="https://churchofconsensus.org" target="_blank ">churchofconsensus.org</a>
            </li>
            <li>
              <a href="https://twitter.com/meta_cartel" target="_blank">metacartel</a>
            </li>
            <li>
              <a href="https://opensea.io/" target="_blank">opensea.io</a>
            </li>
            <li>
              <a href="https://colony.io/" target="_blank">colony.io</a>
            </li>
            <li>
              <a href="https://www.astroledger.org" target="_blank">astroledger.org</a>
            </li>
            <li>
              <a href="https://www.nervos.org/" target="_blank">Nervos Network</a>
            </li>
            <li>
              <a href="https://token.im/" target="_blank">imToken</a>
            </li>
          </ul>
        </div>

        <div class="col-md-4 col-xs-12 communityColumn">
          <strong>{{ $t("m.donations")}}</strong>
          <ul>
            <li>
              <a href="https://www.grassrootseconomics.org" target="_blank">grassrootseconomics.org</a>
            </li>
            <li>
              <a
                href="https://helpdesk.unicef.org.nz/help/donate-to-unicef-via-cryptocurrencies"
                target="_blank"
              >unicef.org</a>
            </li>
            <li>
              <a href="https://www.bitcoinvenezuela.com" target="_blank">bitcoinvenezuela.com</a>
            </li>
            <li>
              <a href="https://eff.org" target="_blank">eff.org</a>
            </li>
            <li>
              <a href="https://enlawfoundation.org" target="_blank">enlawfoundation.org</a>
            </li>
          </ul>
        </div>
      </div>
    </section>

    <cookiebanner></cookiebanner>
  </div>
</template>

<script>
import { mapGetters, mapState } from "vuex";
import * as actions from "../../store/actions";
import Buidlers from "../../components/widgets/Buidlers";
import Card from "../../components/widgets/Card";
import Samplequote from "../../components/widgets/SampleQuote";
import Benefactor from "../../components/widgets/Benefactor";
import Cookiebanner from "../../components/widgets/CookieBanner";
import WindyTitle from "../widgets/WindyTitle";

export default {
  name: "home",
  components: {
    Card,
    Benefactor,
    Samplequote,
    Buidlers,
    Cookiebanner,
    WindyTitle
  },
  data() {
    return {
      cardData: {
        extra: "",
        giftAmount: 0.1,
        message:
          "We don't need more fiat, but love for this holiday!\n\n Enjoy the festive season.",
        BenefactorIndex: 1,
        accountCreatedCard: false,
        tokenId: 28,
        name: "Privacy Forever",
        description: "Forever be with me my privacy.",
        image:
          "https://ipfs.infura.io/ipfs/QmNRUjkackbZcnkxhjDcF81dAHDdNK9yuZShHPGCi4Eih4",
        attributes: { artist: "Hernan Wave" },
        external_uri: "https://radi.cards",
        cardIndex: 11
      }
    };
  },
  computed: {
    ...mapState([
      "totalSupply",
      "totalGifted",
      "usdPrice",
      "cards",
      "benefactors"
    ])
  },
  methods: {}
};
</script>

<style lang="scss" scoped>
@import "../../styles/variables.scss";
@import "../../styles/mixins.scss";

// h1 {
//   font-size: 2.5rem !important;
// }
// @media (min-width: 544px) {
//   h1 {
//     font-size: 0.1rem !important;
//   }
// }

// @media (min-width: 768px) {
//   h1 {
//     font-size: 1.5rem;
//   }
// }

// @media (min-width: 992px) {
//   h1 {
//     font-size: 2.0rem;
//   }
// }

// @media (min-width: 1200px) {
//   h1 {
//     font-size: 2.5rem;
//   }
// }

.blockquote--hero {
  margin-bottom: 1rem !important;
  img {
    max-width: 100%;
  }
}
// Page-specific style
.hero {
  font-size: 2.5rem !important;
  color: $darkgray;
  @media (min-width: 544px) {
    font-size: 2.5rem !important;
  }

  @media (min-width: 768px) {
    font-size: 3rem !important;
  }

  @media (min-width: 992px) {
    font-size: 3.5rem !important;
  }

  @media (min-width: 1200px) {
    font-size: 4rem !important;
  }
}
.section--hero .cheeky-comment {
  position: absolute;
  top: 140%;
  left: 40%;
  width: 14rem;
  transform: rotate(6deg);

  font-weight: bold;

  @include tabletAndUp() {
    top: 110%;
    left: 70%;
    width: 20rem;
    font-size: 1.5rem;
    line-height: 1.5rem;
  }

  &:before {
    content: "";
    position: absolute;
    top: -3rem;
    right: 100%;
    width: 3.5rem;
    height: 3.5rem;
    background: url("/static/images/red-arrow.svg");
    background-size: 85%;
    background-repeat: no-repeat;

    @include tabletAndUp() {
      width: 5rem;
      height: 5rem;
    }
  }
}
.section--credits {
  h5 {
    margin-bottom: 0.1rem;
    padding: 0;
    color: $darkgray;
  }
  .container {
    display: flex;
    flex-direction: column;

    .col {
      margin-bottom: 2rem;
    }

    @include tabletAndUp() {
      flex-direction: row;

      .col {
        flex-basis: percentage(1/3);
      }
    }
  }
}

.steps {
  display: flex;
  justify-content: space-between;

  h5 {
    font-size: 25px;
  }

  span {
    font-size: 20px;
  }

  img {
    margin-bottom: 10px;
  }
}

.stepMargin {
  @media (max-width: 767px) {
    margin-top: 2rem;
  }
}

.smaller-heading {
  @media (max-width: 767px) {
    font-size: 2rem !important;
  }
}

.stepIcon {
  @media (max-width: 767px) {
    float: left !important;
    padding-right: 2rem;
  }
  @media (max-width: 352px) {
    width: 35%;
    padding-bottom: 0.6rem;
    padding-top: 0.6rem;
  }
}

.hide-mobile {
  @media (max-width: 767px) {
    display: none;
  }
}

.communityColumn {
  @media (max-width: 767px) {
    margin-top: 2rem;
  }
}

.compatible {
  h5 {
    margin-top: 3rem;
    font-size: 15px;
  }

  .icons {
    display: flex;
    margin-top: 0;
    @media (max-width: 560px) {
      padding-bottom: 2rem;
    }

    div {
      margin-right: 50px;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      @media (max-width: 560px) {
        margin-right: 2rem;
      }

      img {
        margin-top: 20px;
        height: 40px;
        width: 40px;
        margin-bottom: 10px;
      }

      span {
        font-family: Helvetica;
        line-height: 11px;
        font-size: 12px;

        color: #414141;
      }
    }
  }
}
</style>
