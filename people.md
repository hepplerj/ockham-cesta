---
title: People
permalink: /people/
layout: page
...

<script type="text/javascript">

  window.onload = function() { init() };

  var public_spreadsheet_url = 'https://docs.google.com/spreadsheet/pub?hl=en_US&hl=en_US&key=1pxA8TOXolXcsVmjOl6MCJRRjDTgeAQwLVyPb_hC_9FU&output=html';

  function init() {
      Tabletop.init( { key: public_spreadsheet_url,
                       callback: showInfo,
                       simpleSheet: false } )
  }

  function showInfo(data, tabletop) {
    //console.log("full data", data);
    var tableNames = tabletop.sheets("people").elements;
    //console.log("tableNames", tableNames);
    var names = Object.keys(tableNames);
    //console.log("names", names);

    function getName(d) {
      var name = d['full_name'];
      return name;
    }

    var combined = [];
    tableNames.forEach(function(d) {
      console.log("foreach", d);
       var c = {
        name: getName(d),
        department: d['Department']
       }
       combined.push(c);
      //var entries = name; 
      //console.log("entries", entries);
    })
    console.log(combined);

    //console.log("Successfully processed!");
    //console.log(tabletop.sheets('people'));
    //console.table(data.sheets("people"));
  }

</script>
