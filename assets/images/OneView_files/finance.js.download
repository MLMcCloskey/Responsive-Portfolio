$("#homeButtons").on("click", "#financeBtn", function () {
    $("#homeButtons").empty();
    $("#homeButtons").append(homeBtn + '<button type="button" class="btn btn-success" id="stocksBtn">STOCKS</button> <br> <button type="button" class="btn btn-primary" id="cryptoBtn">CRYPTO</button> <br> <button type="button" class="btn btn-danger" id="financeNewsBtn">NEWS</button>');
});

$("#homeButtons").on("click", "#stocksBtn", function () {
    $("#homeButtons").empty();
    $("#homeButtons").prepend(homeBtn);
    $("#map").append('<iframe src="https://investingwidgets.com/leading-stocks?theme=darkTheme" width="80%" height="330" frameborder="0" allowtransparency="true" marginwidth="0" marginheight="0"></iframe><div class="poweredBy" style="font-family: Arial, Helvetica, sans-serif;">')
});

$("#homeButtons").on("click", "#cryptoBtn", function () {
    $("#homeButtons").empty();
    $("#homeButtons").prepend(homeBtn);
    $("#map").append('<iframe src="https://investingwidgets.com/top-cryptocurrencies?theme=darkTheme&cols=symbol,priceUsd,vol24,priceBtc,chg24,chg7" width="80%" height="330" frameborder="0" allowtransparency="true" marginwidth="0" marginheight="0"></iframe><div class="poweredBy" style="font-family: Arial, Helvetica, sans-serif;">')
});

$("#homeButtons").on("click", "#financeNewsBtn", function () {
    $("#homeButtons").empty();
    $("#homeButtons").prepend(homeBtn);

    var queryURL = "https://api.nytimes.com/svc/topstories/v2/business.json";
    queryURL += '?' + $.param({
        'api-key': "c4e81bd625614e2ba183058baa5c64a5"
    });
    $.ajax({
        url: queryURL,
        method: 'GET',
    }).done(function (result) {
        console.log(result);

    for(i=0; i<5; i++){
        var links = $('<a>').attr('href', result.results[i].url).text(result.results[i].title);
        $("#map").append(links).append('<hr>')
    };

    });
});