## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/rajank17/dat608_Module5/edit/master/README.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
<html>

<!--
    
    Note to Students:
        This is a very short introduction to using Javascript in the browser.
        To see this as a webpage, you have to start a *Local Web Server*. There are many ways to do this: since you all have python installed, we will use python.
        - Open terminal
        - 'cd' into the directory where this html file is (js_in_webpage.html)
        - Type the following into the terminal and hit 'enter':
            python -m SimpleHTTPServer
            your server should read something like: Serving HTTP on 0.0.0.0 port 8000 ...
        - now go to any browser and type in the HTTP address and the filename: something like:
            http://0.0.0.0:8000/js_in_webpage.html
            or
            http://localhost:8000/js_in_webpage.html
        
        - Congrats: you now have a local HTTP server running. Now, every time you change this file and save it, when you reload the browser you will see your changes!
-->

<head><title>DATA 608 Week 6: Krishna Rajan</title></head>

<body>
  
<h1> Part 1a</h1>
<p>Reverse Word or Phrase</p>
    <script type="text/javascript">
    function reverse(str){
        var splitString = str.split("");
        var reverseArray = splitString.reverse();
        var joinArray = reverseArray.join("");
        return joinArray;
    };
    function reverser(){
            var x = document.getElementById("targeta");
            x.innerHTML = reverse(document.getElementById('str').value);
        }
    </script>
    <form name="mystring">
        <input id="str" type="str" size="20">
        <input type="button" value="reverse" onClick="reverser();">
    </form>
    <br>
    <div id="targeta"></div>
    </body>

<script type="text/javascript">
    function list_multiples(input_number){
       table_data = "<table>"
    
        for (var i = 1; i < 6; i++){
         
            var num1 = input_number * (4*i - 3);
            var num2 = input_number * (4*i - 2);
            var num3 = input_number * (4*i - 1);
            var num4 = input_number * (4*i - 0);
            row_data =    
            '<tr>' + 
            '<td>' + num1 + '</td>' + 
            '<td>' + num2 + '</td>' + 
            '<td>' + num3 + '</td>' + 
            '<td>' + num4 + '</td>' + 
            '</tr>'; 
            table_data = table_data + row_data
        }
        table_data = table_data + "</table>"
    return table_data; 
    }
    </script>



<script type="text/javascript">
    function perfrom_multiples(){
        var t = document.getElementById("target2");
        t.innerHTML = list_multiples(document.getElementById('number_input').value);
    }
</script>

<h1> Part 1b</h1>
<p>List first 20 multiples of number</p>

<form>
    <input id="number_input" type="number" size="4">
    <input type="button" value="Number" onClick="perfrom_multiples();">
</form>
</p>
<div id="target2"></div>

<h1> Part 2</h1>
<p>President Height & Weight</p>

 <script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/d3/4.7.4/d3.min.js"></script>
    </head>
    <body>
    <script type="text/javascript">
        function get_presidents_data(){
            d3.csv("https://raw.githubusercontent.com/charleyferrari/CUNY_DATA_608/master/module5/data/presidents.csv", function(data) {
                var row_data = ""; 
                data.forEach(function(d) {
                    row_data = row_data + 
                    "<tr>" + 
                    "<td>" + d.Name + "</td>" + 
                    "<td>" + d.Height + "</td>" + 
                    "<td>" + d.Weight + "</td>" + "</tr>"
                });
                display_president_table(row_data); 
            });
        }
        function display_president_table(row_data){
            var t = document.getElementById("target1");
            t.innerHTML = "<table>" + row_data + "</table>"; 
        }
        function search_president(president_name){
            d3.csv("https://raw.githubusercontent.com/charleyferrari/CUNY_DATA_608/master/module5/data/presidents.csv", function(data) {
            //console.log(data)
            var selected_object = data.filter(function(d) 
            { 
                if (d["Name"].toLowerCase() == president_name.toLowerCase()) 
                { 
                    return d;
                } 
            });
            //console.log(selected_object[0].Name);
            if(selected_object.length > 0){
                window.alert("President " + selected_object[0].Name + ":  Height = " + selected_object[0].Height + ", Weight = " + selected_object[0].Weight);
            }
            else{
                window.alert("President not found in database.")
            }
            });
        }
    function president_check(){
        search_president(document.getElementById('president_name').value);
    }
    </script>

<script type="text/javascript">
    get_presidents_data()
</script>

<div id="target1"></div>
<p>
<form>
    <input id="president_name" type="string" size="50"    >
    <input type="button" value="Get president height and weight" onClick="president_check();">
</form>
</p>

</body>
</html>
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/rajank17/dat608_Module5/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
