# JsonLd-test
The repository contains simple web application, with one test controller, where the instantiation of JSONLDParser is tested.
In order to test the instantiation of the JsonLdParser simple add '/test' at the end of the Url and press enter.
The '/test' request is being mapped to the test contoller  which looks like this:

public class TestController {

    @GetMapping
    public ModelAndView getTestData() {
        ModelAndView mv = new ModelAndView();
        mv.setViewName("test");
        mv.getModel().put("data", "Welcome home man");

        RDFParser parser = Rio.createParser(RDFFormat.JSONLD);
        
        return mv;
    }
}

If the creation of the parser is successfull you will get a page with 'JSONLDParser successfully created!'.
Otherwise you will get a full stacktrace error of the exception.
