<template>
  <section class="app-leadin container">
    <div class="first">
      <p>
        Pehr Strand (c. 1758–1826) var orgel- och flöjtursbyggare i Stockholm
        kring sekelskiftet 1800. Strand fick privilegium att bygga spelur 1791,
        och lämnade 1824 över sin verkstad till sonen Pehr Zacharias Strand
        (1797–1844). Denna webbportal är en redovisning av ett forskningsprojekt
        och samtidigt en källa till information om Pehr Strand och i synnerhet
        hans flöjtur.
      </p>
    </div>
    <!--   <div class="second">
      <p>
       Flöjtur är en klocka med ett mekaniskt spelverk som kan spela musikstycken programmerade på en stiftvals. 
       Termen flöjtur anger också att tonen alstras med hjälp av pipor på samma sätt som i traditionella piporglar. 
       I Sverige byggdes denna typ av flöjtur främst under andra hälften av 1700-talet och en bit in på 1800-talet, 
       där Pehr Strand var en av de mest framgångsrika byggarna.
      </p>
    </div> -->
  </section>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.app-leadin {
  height: auto;
  margin: 50px auto 30px;
  line-height: 1.2;
  text-align: center;
}

.first {
  font-size: 30px;
}

.second {
  font-size: 22px;
}

@media screen and (min-width: 1000px) {
  .app-leadin {
    display: flex;
    align-items: center;
  }

  .first {
    flex: 1;
    padding-right: 30px;
    //border-right: 0.5px solid;
    //text-align: right;
    text-align: center;
  }

  .second {
    flex: 1;
    margin-left: 30px;
    text-align: left;
  }

  .first,
  .second {
    & > :first-child {
      margin-top: 0;
    }
    & > :last-child {
      margin-bottom: 0;
    }
  }
}
</style>
