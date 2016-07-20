# lightbox



     <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.3/jquery.min.js"></script>
     
##HTML

      <a class="openMyligthBox" href="#myligthBoxId">Open</a>
      <div class="fullBg">
      	<div class="myligthBox" id="myligthBoxBgId">
      		<a href="#" class="closeMyligthBox" title="Close"><i class="fa fa-times" aria-hidden="true"></i></a>
      	</div>
      </div>

##CSS

    	html,body{ margin: 0; padding: 0;}
    	.fullBg{display: none; position: fixed; top:0; left: 0; width: 96%; padding: 0 2%;  height: 100%; background: rgba(0,0,0,0.3); z-index: 9998;    }
    	
    	.myligthBox h2{ color:#07c; margin: 0; padding: 10px 0; font-size: 16px; }
    	.myligthBox p{  margin: 0; padding-bottom: 10px;}
    	.myligthBox span{color:#07c;}
    	
    	.myligthBox{ margin: 10% auto 0; padding: 15px 2%;  max-width:600px; min-height: 450px; background: #fff; position: relative; z-index: 9999;  font-size: 16px; line-height: 1.5;	-webkit-border-radius: 6px;	-moz-border-radius: 6px;	border-radius: 6px;
    	}
    	 .myligthBox .closeMyligthBox{display: inline-block; padding: 0px 10px;text-align: center;font-size: 22px;background: #fff;background: rgba(255,255,255,0.6);
        color: #333;border-radius: 50%; position: absolute;top: 5px;right: 5px;}
    		
    	@media screen and ( max-width: 990px){
    		.myligthBox{ margin:10px 0; padding: 10px 0; max-width: inherit; height:  440px; min-height:inherit; overflow-y:auto; }
    	}

##Javascript

        $(function(){
        
        	myligthBox($(".openMyligthBox"),{ startShow:true });
        
        
        	function myligthBox($this,obj){
        
        		var _show = obj.startShow || false;
        		if( _show ){
        			$this.add('.fullBg').show();
        		}
        
        		$this.click(function(){
        			$($(this).attr("href")).add('.fullBg').fadeIn();
        			$("body").css("overflow","hidden");
        			return false;
        		});
        
        		$('.closeMyligthBox').click(function(){
        			$(this).parents(".fullBg").hide();
        			$("body").css("overflow","inherit");
        			return false;
        		});
        
        		$(".myligthBox").click(function(event){
        			event.stopPropagation();
        		});
        	}
        });
