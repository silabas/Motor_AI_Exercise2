# Motor AI Exercise2

This exercise includes writing a Python script that combines 3 vector data (road bounds, road markings, buildings) into a single raster RGB mask with following pixel values:

- road bound: [0, 0, 200]
- buildings: [255, 0, 0]
- broken line: [0, 20, 10]
- cycle lane: [0, 40, 0]
- dashed line: [0, 45, 70]
- pedestrian crossing: [0, 100, 0]
- solid line: [0, 45, 0]
- stop line: [0, 85, 0]
