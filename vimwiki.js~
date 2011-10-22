$(document).ready(function() {
    if (window.innerWidth >= 460) {
        var toggler = $('<div class="toggler" title="点击展开/收起，Shift+Z 隐藏或打开">目录</div>'),
        toc = $('.toc');
        toc.wrap('<div class="tocWrap">');

        $('.tocWrap').prepend(toggler)
        .delay(500)
        .fadeTo(500, '0.25')
        .hover(function() {
            $(this).stop().fadeTo(300, '0.9');
        }, function() {
            $(this).stop().fadeTo(300, '0.25');
        });

        $('html').keypress(function(e) {
            if (e.shiftKey && (e.charCode || e.keyCode) == '90') {
                e.preventDefault();
                $('div.tocWrap').toggle(200);
            }
        });

        toggler.click(function() {
            $('div.toc').slideToggle(300);
        });
    }

    //外链处理
    $('a[href]').each(function() {
        if (this.href.indexOf(window.location.host) == -1) $(this).attr({target: '_blank', title: this.href });
    });

    $('a[href^=#][href!=#]').click(function() {

        var target = document.getElementById(this.hash.slice(1));

        if (!target) return;

        var targetOffset = $(target).offset().top;
        $('html,body').animate({scrollTop: targetOffset}, 400);

        return false;
    });

    //lesser
    $('div.lesser .hd').click(function() { $(this).next().slideToggle(300); });

    //把< 转为html实体>

    //Google自定义搜索
    $.getScript('http://www.google.com/jsapi', function() {
        google.load('search', '1', {language: 'zh-CN', 'callback': cseloaded });
    });

    function cseloaded() {
        var customSearchControl = new google.search.CustomSearchControl('013996024720219627519:n_9lss7xao0');
        customSearchControl.setResultSetSize(5);
        customSearchControl.setNoResultsString('哎哟喂，找不到这个东东呢……');

        var options = new google.search.DrawOptions();
        options.setAutoComplete(true);
        customSearchControl.draw('cse');

        var input = document.querySelector('input.gsc-input');
        input.style.cssText = '';
        input.className = 'gsc-input cesbg';
        input.onfocus = function() {
            if (input.className.indexOf('cesbg') >= 0) input.className = 'gsc-input';
        };
        input.onblur = function() {
            if (input.value == '') input.className = 'gsc-input cesbg';
        };
    };

});

