<template>
    <!-- side left -->
    <div class="vertical-menu">
        <div data-simplebar class="h-100">
            <div id="sidebar-menu">
                <ul class="metismenu list-unstyled" id="side-menu">
                    <li class="menu-title">Menu</li>
                    <li>
                        <router-link to="/student/dashboard" class="waves-effect">
                            <div class="d-inline-block icons-sm ml-1"><i class="fas fa-chart-line" style="color: #3051d3;"></i></div>
                            <span>Dashboard</span>
                        </router-link>
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>
<script>
import metisMenu from 'metismenu';
export default {
    mounted() {
        $(function() {
            /*sidebar*/
            "use strict";
            $("#side-menu").metisMenu(),
                $("#vertical-menu-btn").on("click", function(t) {
                    t.preventDefault(), $("body").toggleClass("sidebar-enable"), 992 <= $(window).width() ? $("body").toggleClass("vertical-collpsed") : $("body").removeClass("vertical-collpsed");
                }),
                $("#sidebar-menu a").each(function() {
                    var t = window.location.href.split(/[?#]/)[0];
                    this.href == t &&
                        ($(this).addClass("active"),
                            $(this).parent().addClass("mm-active"),
                            $(this).parent().parent().addClass("mm-show"),
                            $(this).parent().parent().prev().addClass("mm-active"),
                            $(this).parent().parent().parent().addClass("mm-active"),
                            $(this).parent().parent().parent().parent().addClass("mm-show"),
                            $(this).parent().parent().parent().parent().parent().addClass("mm-active"));
                }),
                $(".navbar-nav a").each(function() {
                    var t = window.location.href.split(/[?#]/)[0];
                    this.href == t &&
                        ($(this).addClass("active"),
                            $(this).parent().addClass("active"),
                            $(this).parent().parent().addClass("active"),
                            $(this).parent().parent().parent().parent().addClass("active"),
                            $(this).parent().parent().parent().parent().parent().addClass("active"),
                            $(this).parent().parent().parent().parent().parent().parent().addClass("active"),
                            $(this).parent().parent().parent().parent().parent().parent().parent().addClass("active"));
                }),
                $(".right-bar-toggle").on("click", function(t) {
                    $("body").toggleClass("right-bar-enabled");
                }),
                $(document).on("click", "body", function(t) {
                    0 < $(t.target).closest(".right-bar-toggle, .right-bar").length || $("body").removeClass("right-bar-enabled");
                }),
                $(".dropdown-menu a.dropdown-toggle").on("click", function(t) {
                    return $(this).next().hasClass("show") || $(this).parents(".dropdown-menu").first().find(".show").removeClass("show"), $(this).next(".dropdown-menu").toggleClass("show"), !1;
                }),
                $(function() {
                    $('[data-toggle="tooltip"]').tooltip();
                }),
                $(function() {
                    $('[data-toggle="popover"]').popover();
                }),
                Waves.init();
        });
    }
}

</script>
