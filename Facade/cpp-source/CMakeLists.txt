cmake_minimum_required(VERSION 3.5)
project(Facade)

add_executable(
        Facade
        facades/BurgerFacade.cpp
        facades/IsaacFacade.cpp
        facades/IsaacFacade.h
        facades/Facade.cpp
        facades/Facade.h
        main.cpp
)

link_directories(../../lib)

target_include_directories(Facade PRIVATE ../../)
target_include_directories(Facade PRIVATE ../../AbstractFactory/cpp-source/rooms)
target_link_libraries(Facade serializers isaac_rooms isaac_factories burger_shop)

install(TARGETS Facade serializers isaac_rooms isaac_factories burger_shop
	RUNTIME DESTINATION bin
	LIBRARY DESTINATION lib
	ARCHIVE DESTINATION lib
)
