<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css" type="text/css">
    <link rel="stylesheet" href="https://static.pingendo.com/bootstrap/bootstrap-4.3.1.css">
</head>

<body style="">
    <nav class="navbar navbar-light bg-dark">
        <div class="container d-flex justify-content-center">
            <a class="navbar-brand text-primary" href="#">
                <img src="imgs/piccargo-logo-1080.png" class="d-inline-block align-top" alt="" width="70" height="70"></a>
        </div>
    </nav>
    <div class="d-flex flex-column justify-content-center align-items-center">
        <div class="container-fluid" style="">
            <div class="row">
                <div class="col-md-12 p-2 d-flex flex-column justify-content-center align-items-center" style="	height: 528px;	width: 1200px;	background-image: linear-gradient(to bottom, rgba(0,0,0,0.2), rgba(27, 27, 27, 0.8)), url(&quot;imgs/background-home.jpeg&quot;);	background-position: top left, center;	background-size: 100%, cover;	background-repeat: repeat, no-repeat;">
                    <h1 class="text-light">
                        <h1 href="" class="typewrite text-light" data-period="2000" data-type="[ &quot;a melhor.&quot;, &quot;a empresa do futuro.&quot;, &quot;a PicCargo.&quot; ]">
                            <span class="wrap"></span>
                        </h1>
                    </h1>
                </div>
            </div>
        </div>
    </div>
    <script type="text/javascript">
        var TxtType = function(el, toRotate, period) {
            this.toRotate = toRotate;
            this.el = el;
            this.loopNum = 0;
            this.period = parseInt(period, 10) || 2000;
            this.txt = '';
            this.tick();
            this.isDeleting = false;
        };
        TxtType.prototype.tick = function() {
            var i = this.loopNum % this.toRotate.length;
            var fullTxt = this.toRotate[i];
            if (this.isDeleting) {
                this.txt = fullTxt.substring(0, this.txt.length - 1);
            } else {
                this.txt = fullTxt.substring(0, this.txt.length + 1);
            }
            this.el.innerHTML = '<span class="wrap">' + "Estamos criando " + this.txt + '</span>';
            var that = this;
            var delta = 150 - Math.random() * 100;
            if (this.isDeleting) {
                delta /= 2;
            }
            if (!this.isDeleting && this.txt === fullTxt) {
                delta = this.period;
                this.isDeleting = true;
            } else if (this.isDeleting && this.txt === '') {
                this.isDeleting = false;
                this.loopNum++;
                delta = 300;
            }
            setTimeout(function() {
                that.tick();
            }, delta);
        };
        window.onload = function() {
            var elements = document.getElementsByClassName('typewrite');
            for (var i = 0; i < elements.length; i++) {
                var toRotate = elements[i].getAttribute('data-type');
                var period = elements[i].getAttribute('data-period');
                if (toRotate) {
                    new TxtType(elements[i], JSON.parse(toRotate), period);
                }
            }
            // INJECT CSS
            var css = document.createElement("style");
            css.type = "text/css";
            css.innerHTML = ".typewrite > .wrap { border-right: 0.08em solid black}";
            document.body.appendChild(css);
        };
        Resources
    </script>
    <script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.6/umd/popper.min.js" integrity="sha384-wHAiFfRlMFy6i5SRaxvfOCifBUQy1xHdJ/yoi7FRNXMRBu5WHdZYu1hA6ZOblgut" crossorigin="anonymous"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js" integrity="sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM" crossorigin="anonymous"></script>
</body>

</html>
