<!DOCTYPE html>
<html lang="en">
<head>
  <title>Bootstrap Example</title>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css">
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
  <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js"></script>
</head>
<body>

<div class="container-fluid">
  <h1>Hello World!</h1>
  <p>Resize the browser window to see the effect.</p>
  <div class="row">
    <div class="col-xs-9 col-md-7" style="background-color:red;">.col-xs-9 .col-md-7</div>
    <div class="col-xs-3 col-md-5" style="background-color:lavender;">.col-xs-3 .col-md-5</div>
    <p><div class="popup-only-box popup-box-on" id="popup-before-pop">
  <div class="popup-only-head">

    <a class="btn btn-info btn-block btn-social btn-twitter" id="addClass" onClick="popup(this.id)">
             Popup Tweets
    </a>

  </div>
</div>

<div class="popup-box" id="popup-after-pop">
  <div class="popup-head">



  <a class="btn btn-info btn-block btn-social btn-twitter" id="removeClass" onClick="popdown(this.id)">
      Popdown Tweets
  </a>


  </div>

  <div class="popup-messages">

<a class="twitter-timeline" data-width="220" data-link-color="#981CEB" href="https://twitter.com/WillamLomax?ref_src=twsrc%5Etfw">Tweets by WillamLomax</a> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

  </div>


</div>




<script type="text/javascript">
function popdown(clicked_id)
{
    $afterpop = $('#popup-after-pop');
    $beforepop = $('#popup-before-pop');

    $afterpop.removeClass('popup-box-on');
    $beforepop.addClass('popup-box-on');

}
</script>

<script type="text/javascript">
function popup(clicked_id)
{
    $afterpop = $('#popup-after-pop');
    $beforepop = $('#popup-before-pop');

    $afterpop.addClass('popup-box-on');
    $beforepop.removeClass('popup-box-on');

}
</script>
  </div>
  <div class="row">
    <div class="col-xs-6 col-md-10" style="background-color:lavenderblush;">.col-xs-6 .col-md-10</div>
    <div class="col-xs-6 col-md-2" style="background-color:lightgrey;">.col-xs-6 .col-md-2</div>
  </div>
  <div class="row" style="background-color:lightcyan;">
    <div class="col-xs-6">.col-xs-6</div>
    <div class="col-xs-6">.col-xs-6</div>
  </div>
</div>

</body>
</html>
