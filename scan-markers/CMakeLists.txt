QT4_WRAP_CPP(moc_sources
  GuiController.h
  ModelAcquisitionController.h
  FiltersWindow.h
  RawImagesWindow.h
  ModelAcquisitionWindow.h
)

QT4_WRAP_UI(uic_sources
  RawImagesWindow.ui
  FiltersWindow.ui
  ModelAcquisitionWindow.ui
)

INCLUDE_DIRECTORIES(${CMAKE_CURRENT_BINARY_DIR} ${CMAKE_CURRENT_SOURCE_DIR})
SET(scan_markers_sources ${moc_sources} ${uic_sources}
               scan_markers.cpp
               RawImagesWindow.h RawImagesWindow.cpp
               GuiController.cpp GuiController.h
               ModelAcquisitionController.cpp ModelAcquisitionController.h
               FiltersWindow.cpp FiltersWindow.h
               ModelAcquisitionWindow.cpp ModelAcquisitionWindow.h)

NESTK_ADD_EXECUTABLE(rgbd-scan-markers ${scan_markers_sources})
TARGET_LINK_LIBRARIES(rgbd-scan-markers nestk)
