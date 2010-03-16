LazyHighCharts
==============

plugin for make highcharts a la ruby

  highcharts:http://www.highcharts.com/demo/

Some Ideas & code taken from 

  flotomatic

  open_flash_chart_lazy

requires:
  
  jquery, tested in rails 2.3.x and 3.0.0
  

Usage
=======

 Usage in Controller:
  
     @h = HighChart.new('graph') do |f|
        f.series('John', [3, 20, 3, 5, 4, 10, 12 ,3, 5,6,7,7,80,9,9])
        f.series('Jane', [1, 3, 4, 3, 3, 5, 4,-46,7,8,8,9,9,0,0,9] )
      end
 

  Without overriding option:  
 
     @h = HighChart.new('graph') do |f|
      .....
          f.options[:chart][:defaultSeriesType] = "area"
          f.options[:chart][:inverted] = true
          f.options[:legend][:layout] = "horizontal"
          f.options[:x_axis][:categories] = ["uno" ,"dos" , "tres" , "cuatro"]
     ......

  Overriding entire option: 

     @h = HighChart.new('graph') do |f|
       .....
          f.x_axis(:categories => @days.reverse! , :labels=>{:rotation=>-45 , :align => 'right'})
          f.series_type("spline")
       .....


  Usage in layout:
      
     <%= javascript_include_tag :defaults %>
     <%= javascript_include_tag :high_charts %>
     <!--[if IE]>
      <%= javascript_include_tag :ie_high_charts %>
     <![endif]-->
      
  Usage in view:
  
    <%= high_chart("my_id", @h) %>


  Option reference:

     http://www.highcharts.com/ref/
    


Copyright (c) 2009 [Miguel Michelson Martinez], released under the MIT license
