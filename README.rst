===========================
python-aqi - AQI conversion
===========================

A library to convert between AQI value and pollutant concentration
(µg/m³ or ppm) using the following algorithms:

* United States Environmental Protection Agency (EPA)
* China Ministry of Environmental Protection (MEP)

Usage
-----

Convert a pollutant to its IAQI (Intermediate Air Quality Index)::

    import aqi
    myaqi = aqi.to_iaqi(aqi.POLLUTANT_PM25, '12', algo=aqi.ALGO_EPA)


Get an AQI out of several pollutant concentrations, default algorithm is EPA::

    import aqi
    myaqi = aqi.to_aqi([
        (aqi.POLLUTANT_PM25, '12'),
        (aqi.POLLUTANT_PM10, '24'),
        (aqi.POLLUTANT_O3_8H, '0.087')
    ])

Convert an IAQI to its pollutant concentration::

    import aqi
    mycc = aqi.to_cc(aqi.POLLUTANT_PM25, '22', algo=aqi.ALGO_EPA)


Resource
--------

* EPA AQI: Technical Assistance Document for the Reporting of Daily Air
* Quality – the Air Quality Index (AQI) (September 2012) found at http://www.epa.gov/airnow/aqi-technical-assistance-document-sep2012.pdf
* MEP AQI:

    * GB3095—2012 (2012/02/29) found at http://www.mep.gov.cn/gkml/hbb/bwj/201203/t20120302_224147.htm
    * HJ633-2012 (2012/02/29) found at http://www.zzemc.cn/em_aw/Content/HJ633-2012.pdf

License
-------

python-aqi is published under a BSD 3-clause license, see the LICENSE file
distributed with the project.