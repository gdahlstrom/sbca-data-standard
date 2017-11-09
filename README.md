# Welcome to the SBCA-Data-Standard Repository

This is where example submissions and discussion are taking place to develop standard data formats for the Structural Prefabricated Building Component Industry

# What is a Data Standard?

From Wikipedia: "A standard data model or industry standard data model (ISDM) is a data model that is widely applied in some industry, and shared amongst competitors to some degree. They are often defined by standards bodies, database vendors or operating system vendors.

When in use, they enable easier and faster information sharing because heterogeneous organizations have a standard vocabulary and pre-negotiated semantics, format, and quality standards for exchanged data. The standardization affects software architecture as solutions that vary from the standard may cause data sharing issues and problems if data is out of compliance with the standard.

Effective standard models have been developed in the banking, insurance, pharmaceutical and automotive industries, to reflect the stringent standards applied to customer information gathering, customer privacy, consumer safety, or just in time manufacturing."

# Examples of other industries that have Data Standards:

* [ISO 10303](https://en.wikipedia.org/wiki/ISO_10303)
* [United States Geological Survey](https://www2.usgs.gov/datamanagement/plan/datastandards.php)

# Questions that need to be answered in order to develop this Data Standard
* What is the scope of this Data Standard? Do we want to standardize only Trusses? or do we include components like Walls? Do we create a specification for layouts, loading, etc?
* How thorough do we want our files to be? (Should we store geometric information in 2D or 3D?, etc.)
* Do we include potentially conflicting information or only the minimum neccessary? (Given the geometry of a truss, do we also include its heel heights? since this can be derived from the geometry?)

# Example

A quick sample of what a data file for a Component might look like (Note member and plate geometries are 3D):

    {
      "Name": "T-1",
      "ComponentType": "RoofTruss",
      "Span": 288.0,
      "NumberOfPlies": 1,
      "TopChordBracingLength": 24.0,
      "BottomChordBracingLength": 120.0,
      "Members": [
        {
          "Name": "B1",
          "Lumber": {
            "NominalThickness": "2",
            "NominalWidth": "4",
            "ActualThickness": 1.5,
            "ActualWidth": 3.5,
            "Length": 96.0,
            "Grade": "Number_2",
            "Species": "Spruce_Pine_Fir",
            "TreatmentType": "None",
            "GradingMethod": "VisuallyGraded",
            "Structure": "Sawn"
          },
          "Geometry": {
            "Vertices": [
              [ 96.0, 1.5, 0.0 ],
              [ 0.0, 1.5, 0.0 ],
              [ 0.0, 1.5, 0.25 ],
              [ 9.75, 1.5, 3.5 ],
              [ 96.0, 1.5, 3.5 ],
              [ 96.0, 0.0, 0.0 ],
              [ 0.0, 0.0, 0.0 ],
              [ 0.0, 0.0, 0.25 ],
              [ 9.75, 0.0, 3.5 ],
              [ 96.0, 0.0, 3.5 ]
            ],
            "Faces": [
              [ 0, 1, 2 ],
              [ 0, 2, 3 ],
              [ 0, 3, 4 ],
              [ 0, 5, 6 ],
              [ 0, 6, 1 ],
              [ 1, 6, 7 ],
              [ 1, 7, 2 ],
              [ 2, 7, 8 ],
              [ 2, 8, 3 ],
              [ 3, 8, 9 ],
              [ 3, 9, 4 ],
              [ 4, 9, 5 ],
              [ 4, 5, 0 ],
              [ 5, 9, 8 ],
              [ 5, 8, 7 ],
              [ 5, 7, 6 ]
            ],
            "Surfaces": [
              [ 0, 1, 2 ],
              [ 3, 4 ],
              [ 5, 6 ],
              [ 7, 8 ],
              [ 9, 10 ],
              [ 11, 12 ],
              [ 13, 14, 15 ]
            ]
          },
          "MemberType": "BottomChord",
          "Length": 96.0,
          "Bracing": null,
          "Angle": 0.0,
          "Pitch": "0/12",
          "CrossSectionalArea": "5.25",
          "TransformationMatrix": [ 1.0, 0.0, 0.0, 0.0, 0.0, 0.0, -1.0, 0.0, 0.0, 1.0, 0.0, 0.0, 0.0, 0.0, 1.5, 1.0 ]
        },
       ...
      ],
      "PlatePairs": [
        {
          "Angle": 0.0,
          "Plate1TransformationMatrix": [ 1.0, 0.0, 0.0, 0.0, 0.0, 1.0, 0.0, 0.0, 0.0, 0.0, 1.0, 0.0, 5.875, 2.0, 1.5, 1.0 ],
          "Plate2TransformationMatrix": [ 1.0, 0.0, 0.0, 0.0, 0.0, 1.0, 0.0, 0.0, 0.0, 0.0, 1.0, 0.0, 5.875, 2.0, -0.0356, 1.0 ],
          "Name": "1",
          "Plate1Geometry": {
            "Vertices": [
              [ -2.5, -2.0, 0.0 ],
              [ -2.5, 2.0, 0.0 ],
              [ 2.5, 2.0, 0.0 ],
              [ 2.5, -2.0, 0.0 ],
              [ -2.5, -2.0, 0.0356 ],
              [ -2.5, 2.0, 0.0356 ],
              [ 2.5, 2.0, 0.0356 ],
              [ 2.5, -2.0, 0.0356 ]
            ],
            "Faces": [
              [ 0, 1, 2 ],
              [ 0, 2, 3 ],
              [ 0, 4, 5 ],
              [ 0, 5, 1 ],
              [ 1, 5, 6 ],
              [ 1, 6, 2 ],
              [ 2, 6, 7 ],
              [ 2, 7, 3 ],
              [ 3, 7, 4 ],
              [ 3, 4, 0 ],
              [ 4, 7, 6 ],
              [ 4, 6, 5 ]
            ],
            "Surfaces": [
              [ 0, 1 ],
              [ 2, 3 ],
              [ 4, 5 ],
              [ 6, 7 ],
              [ 8, 9 ],
              [ 10, 11 ]
            ]
          },
          "Plate2Geometry": {
            "Vertices": [
              [ -2.5, -2.0, 0.0 ],
              [ -2.5, 2.0, 0.0 ],
              [ 2.5, 2.0, 0.0 ],
              [ 2.5, -2.0, 0.0 ],
              [ -2.5, -2.0, 0.0356 ],
              [ -2.5, 2.0, 0.0356 ],
              [ 2.5, 2.0, 0.0356 ],
              [ 2.5, -2.0, 0.0356 ]
            ],
            "Faces": [
              [ 0, 1, 2 ],
              [ 0, 2, 3 ],
              [ 0, 4, 5 ],
              [ 0, 5, 1 ],
              [ 1, 5, 6 ],
              [ 1, 6, 2 ],
              [ 2, 6, 7 ],
              [ 2, 7, 3 ],
              [ 3, 7, 4 ],
              [ 3, 4, 0 ],
              [ 4, 7, 6 ],
              [ 4, 6, 5 ]
            ],
            "Surfaces": [
              [ 0, 1 ],
              [ 2, 3 ],
              [ 4, 5 ],
              [ 6, 7 ],
              [ 8, 9 ],
              [ 10, 11 ]
            ]
          },
          "CenterX": 5.875,
          "CenterY": 2.0,
          "CenterZ": 0.7322,
          "PlatePlacement": "Front_Back",
          "PlateType": "MT20",
          "PlateManufacturer": "MiTek",
          "Width": 4.0,
          "Length": 5.0,
          "Thickness": 0.0356,
          "BaseThickness": 0.0346
        },
      ...
      "Hangers": [
        {
          "Name": "Bearing 2",
          "Width": 3.5,
          "Depth": 1.5,
          "CenterPointX": 186.25,
          "CenterPointY": 0.0
        }
      ],
      "Bearings": [
        {
          "Name": "Bearing 1",
          "Width": 3.5,
          "Depth": 1.5,
          "BearingArea": 5.25,
          "CenterPointX": 1.75,
          "CenterPointY": 0.0,
          "Anchor": "Left",
          "BearingType": "Ledger"
        },
        {
          "Name": "Bearing 2",
          "Width": 3.5,
          "Depth": 1.5,
          "BearingArea": 5.25,
          "CenterPointX": 286.25,
          "CenterPointY": 0.0,
          "Anchor": "Right",
          "BearingType": "Ledger"
        }
      ],
      "LoadSettings": {
        "BuildingCode": "IRC 2015",
        "TPICode": "TPI 2014",
        "TopChordLiveLoading": "78",
        "TopChordDeadLoading": "0",
        "BottomChordLiveLoading": "0",
        "BottomChordDeadLoading": "4",
        "WindSpeed": "90",
        "windExposureCategory": "B",
        "windOccupancyCategory": "II",
        "windEnclosureType": "Enclosed",
        "AverageRoofHeight": "25'",
        "BuildingWidth": "24'",
        "BuildingLength": "45'",
        "MaxTCDL": "6",
        "WindMwfrsZone": "2",
        "WindCcZone": "3",
        "WindLumberDol": "1.6",
        "WindPlateDol": "1",
        "WindMaxBcdl": "6",
        "ExposureRightCantilever": "True",
        "ExposureLeftCantilever": "False",
        "ExposureRightPorch": "True",
        "ExposureLeftPorch": "False",
        "ExposureRightEndVertical": "True",
        "ExposureLeftEndVertical": "False",
        "WindDesignMethod": "ASCE Hybrid All Heights",
        "SnowDesignMethod": "ASCE 7-10",
        "GroundSnowLoad": "20",
        "TerrainCategory": "B",
        "ExposureCategory": "Exposed",
        "OccupancyCategory": "II",
        "ThermalCondition": "1.1",
        "SlipperyRoof": "False",
        "UnbalancedSnow": "2"
      }
    }
