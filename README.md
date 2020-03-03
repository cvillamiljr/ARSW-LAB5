# ARSW-LAB5

### Autores:
- [Cesar Villamil](https://github.com/cvillamiljr)
- [Diego Puerto](https://github.com/Diego23p)

##### Comado para ejecutar: gradle bootRun

### Backend Fixes

- Include within the Gradle dependencies (build.gradle) the 'webjars' of jQuery and Bootstrap (this allows you to have these JavaScript libraries locally when building the project):

![](/BLUEPRINTS_PART1/img/1.PNG)

### Frontend Views

- Create, in the previous directory, the index.html page, only with the basics: title, field for author capture, 'Get blueprints' button, field where the name of the selected author will be displayed, the HTML table where it will be displayed the list of plans (with only the headings), and a field where the total points of the author's plans will be shown. Remember to associate identifiers with these components to facilitate your search through selectors.

![](/BLUEPRINTS_PART1/img/2.PNG)

- In the <head> element of the page, add the references to the jQuery, Bootstrap libraries and the Bootstrap style sheet.

![](/BLUEPRINTS_PART1/img/3.PNG)

- Upload the application (mvn spring-boot: run), and rectify:
    - That the page is accessible from: http://localhost:8080/index.html
    
    ![](/BLUEPRINTS_PART1/img/4.PNG)

    - When you open the browser developer console, you should NOT receive 404 error messages (that is, the JavaScript libraries were loaded correctly).
    
    ![](/BLUEPRINTS_PART1/img/5.PNG)
    
### Frontend Logic

- Copy the provided module (apimock.js) in the same path of the module created before. In this one add more planes (with more points) to the 'burned' authors in the code.

![](/BLUEPRINTS_PART1/img/6.PNG)

- Add the import of the two new modules to the HTML page (after importing the jQuery and Bootstrap libraries):

![](/BLUEPRINTS_PART1/img/7.PNG)

- Have the previously created module keep private:
    - The name of the selected author. 
    - The list of name and size of the plans of the selected author. That is, a list of objects, where each object will have two properties: plan name, and number of points on the plane. Together with a public operation that allows changing the name of the currently selected author.
    
    ![](/BLUEPRINTS_PART1/img/8.PNG)

- Add to the module app.js a public operation that allows updating the list of plans, based on the name of its author (given as a parameter). To do this, said operation must invoke the getBlueprintsByAuthor operation of the provided apimock module, sending as a callback a function that:
    - Take the list of plans, and apply a map function that converts your elements to objects with only the name and number of points.
    
    ![](/BLUEPRINTS_PART1/img/9.PNG)

    - On the resulting list, make another map, which takes each of these elements, and through jQuery add a  element (with the respective ) to the table created in point 4. Consider the jQuery selectors and tutorials available online. For now do not add buttons to the generated rows.
    
    ![](/BLUEPRINTS_PART1/img/10.PNG)
    
    - On any of the two listings (the original, or the one transformed by map), apply a reduce that calculates the number of points. With this value, use jQuery to update the corresponding field within the DOM.
    
    ![](/BLUEPRINTS_PART1/img/11.PNG)
    ![](/BLUEPRINTS_PART1/img/12.PNG)
    
- Associate the previously created operation (that of app.js) with the on-click event of the page query button.

![](/BLUEPRINTS_PART1/img/13.PNG)

- Verify the operation of the application. Start the server, open the HTML5/JavaScript application, and rectify that when entering an existing user, the list of the same is loaded.

![](/BLUEPRINTS_PART1/img/14.PNG)
![](/BLUEPRINTS_PART1/img/15.PNG)
![](/BLUEPRINTS_PART1/img/16.PNG)
