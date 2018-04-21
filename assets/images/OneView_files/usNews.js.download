// powered by News API

//apiKey = 7d26503d0dd74f109690214b2cca28aa
// var pv= ["[[PromiseValue]]"];

$("#homeButtons").on("click", "#usBtn", function(){

    $("#homeButtons").empty();
    $("#homeButtons").prepend(homeBtn);

    var USurl = 'https://newsapi.org/v2/top-headlines?' +
            'country=us&' +
            //   'category=technology&'+
            //   'sources=techcrunch&' +
            'apiKey=7d26503d0dd74f109690214b2cca28aa';


    var req = new Request(USurl);
    fetch(req)
        .then(function(response) {
            console.log(response.json());
        });

    $.get(USurl, function(data){
        console.log(data)
        // $("body").prepend("<div id='news'><ul id='usNewsLinks'></ul></div>")
        for (i=0; i<5; i++){
            var link = $('<a>').attr('href', data.articles[i].url ).text(data.articles[i].title)

            $("#homeButtons").append('<hr>').append(link);
        }
    });
});