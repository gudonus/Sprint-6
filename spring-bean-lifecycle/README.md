Необходимо поправить код проекта, либо файл конфигурации таким образом, 
чтобы все тесты отработали корректно.
P.S. 
1) В тесте `getBean should return bean and call destroy` можно и нужно поправить сам тест 
(постарайтесь решить без прямого обращения к методу destroy). В остальных тестах код теста править не нужно.
2) Для теста `getBean should return bean and call the methods in the correct order` инициализацию 
свойств postProcessBeforeInitializationOrderMessage и postProcessAfterInitializationOrderMessage для бина 
combinedBean необходимо реализовать в бине MyBeanPostProcessor
3) Тест `getBean should return bean and correct preConfiguredProperty` является необязательной задачей 
повышенной сложности. Добавлять аннотации в класс BeanFactoryPostProcessorBean нельзя. 
Для того чтобы тест отработал корректно необходимо реализовать метод postProcessBeanFactory(), 
в котором нужно будет найти методы интерфейсов с аннотацией @PostConstruct и назначить их init-методами для соответствующих классов.