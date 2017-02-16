---------Java Spring--------
Topics covered in this tutorial application


JavaBeanFactory
XMLBeanFactory
Xml Bean “Property”
Property Initialization
ApplicationContext
SetterInjection “<property></property> XML tag
ConstructorInjection <constructor-arg></constructor-arg>
Index based constructor assignment “index=”0” etc.
Object Injection
Inner beans
Alias
List tag, make reference to list values within a bean
Autowiring
Autowire via (setter, constructor, or type injection)
Bean Scopes
Singleton Bean (only once per Spring container)
Prototype Bean (new bean*instance* created with every request or reference)
Web-aware Context Bean Scopes
Request Scope (New Bean per servlet request)
Session Scope (new bean per session)
Global session ( new bean per global HTTP session (portlet context))
ApplicationContextAware - Spring calls “setApplicationContext” and sets the application context to the variable “context” within a bean class.
Bean Definition Inheritance
A Bean definition can be created, one that can be instantiated or one that is abstract and serves as a template for other beans to inherit from
Inherit bean definition via parameter “parent=” to subsequent beans that you wish to inherit the parent bean definition
When inheriting a list from a bean definition configuring the parameter “list merge=true” will not override the list definition but instead add to the inherited list argument
Configuring a parameter in the bean definition “abstract=true” will not instantiate an instance of that bean but instead be used as an abstract bean to be inherited by child bean classes
Lifecycle Callback methods
Methods that can be run when a bean is created and when it is destroyed
“InitializationBean” interface, let the bean know when it is created and to run a method “afterPropertiesSet”
“DisposableBean interface, complete some action when the bean is destroyed
XML parameters “init-method” and “destroy-method” are methods that are called upon creation and destroy of an object that is not tied to Spring itself
BeanPostProcessor runs code for every instantiated bean and its dependencies upon instantiation and after instantiation
The BeanPostProcessor must be declared within the XML configuration file in order to be recognized by the Spring Framework
Properties placeholders
Config.properties file
Reference the values from the config file using conventions “${classname.membervariable}” and refer the them the same way in the config file
Coding to interfaces
By applying interfaces to objects you can override the methods within that interface and interchange specific configurations of the inherited method(s) within the same calling method in your spring structure. For example, by applying an interface “Shape” with a method “draw”, any configurations of a shape that you create, such as triangle or circle, the same method that calls a “shape” object to draw will use the definition of “draw” from child methods that inherit from the parent class. A call to a triangle object that implements shape will draw a 3 sided shape while a circle object that implements shape will draw a circle.
@Required annotation. Using the spring frameworks RequiredAnnotationBeanPostProcessor you may verify that initialization of member variables for beans are indeed instantiated when the bean factory initializes objects within the factory. A error is thrown if a member variable has not been initialized, which helps to verify that an object’s dependencies have been properly initialized, preventing a runtime exception later down the line.
Autowired annotation (AutowiredAnnotationBeanPostProcessor)
First looks for unique bean fitting the required type of the method, second it will look for the name of the bean that matches the member variable being set.
Qualifer, something that can be mentioned in the bean definition to relate a bean with an object
Providing a qualifier annotation to a class method will help the framework detect what beans should be autowired with a specific object
XML namespaces must be configured in the spring.xml
The <context:annotation-config> tag will automatically take care of all AnnotationBeanPostProcessors
JSR250 “Java Specification Request” standard annotations that apply over different technologies and frameworks
@Resource, standard annotation that is defined in the javax package which provides dependency injection by name, if no name is provided it will check for a dependency by the name of the member variable being assigned, similar to autowired
Annotations, PostConstruct and PreDestroy are similar to beaninitialize and beandestroy interfaces. Specify initialization and destruction methods of beans
The @Component tag associated with the Spring Framework is essentially equivalent to the xml configuration of a class bean
Using annotations within a class limits the bean to act as only one configuration with only one specific set of member initialization, therefore in order to use multiple instantiations of the same class with different metadata you must declare either separate classes or define the beans within the spring.xml
Stereotype Annotations, tell Spring additional information besides the bean just being declared as a bean (@Component) which adds information regarding what the bean actually does. It helps with documentation and readability as well.
@Component
@Service
@Repository
@Controller
ResourceBundleMessageSource (Spring class)
Event Handling in Spring
3 main components of Event handling
The event publisher, publishes the event to the context
The event Listener, listens for the event within the context
The event itself, specifies the event being handled
Aspect Oriented Programming
Wrapping aspects around target methods allow a separate aspect configuration file to control the processing of aspects when certain methods are called within the Spring container. This can be helpful to separate common coding functionality from individual classes such as logging, transactions, etc.
Steps in AOP: Write aspects, and configure where they apply
