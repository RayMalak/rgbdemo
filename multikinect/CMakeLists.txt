QT4_WRAP_CPP(moc_sources
  GuiController.h
  View3dWindow.h
  FiltersWindow.h
  RawImagesWindow.h
)

QT4_WRAP_UI(uic_sources
  RawImagesWindow.ui
  View3dWindow.ui
  FiltersWindow.ui
)

INCLUDE_DIRECTORIES(${CMAKE_CURRENT_BINARY_DIR} ${CMAKE_CURRENT_SOURCE_DIR})

SET(rgbd_multikinect_sources ${moc_sources} ${uic_sources}
               main.cpp
               GuiController.cpp GuiController.h
               View3dWindow.cpp View3dWindow.h
               FiltersWindow.cpp FiltersWindow.h
               RawImagesWindow.cpp RawImagesWindow.h
)

NESTK_ADD_EXECUTABLE(rgbd-multikinect ${rgbd_multikinect_sources})
TARGET_LINK_LIBRARIES(rgbd-multikinect nestk)
