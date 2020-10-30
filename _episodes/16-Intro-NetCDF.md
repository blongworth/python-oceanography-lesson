---
title: Introduction to netCDF
teaching: 
exercises: 
questions:
    - "What types of data can be contained in a DataFrame?"
    - "Why is the data type important?"
objectives:
    - "Describe how information is stored in a Python DataFrame."
    - "Define the two main types of data in Python: text and numerics."
    - "Examine the structure of a DataFrame."
    - "Modify the format of values in a DataFrame."
    - "Describe how data types impact operations."
    - "Define, manipulate, and interconvert integers and floats in Python."
    - "Analyze datasets having missing/null values (NaN values)."
    - "Write manipulated data to a file."
keypoints:
    - "Pandas uses other names for data types than Python, for example: `object` for textual data."
    - "A column in a DataFrame can only have one data type."
    - "The data type in a DataFrame’s single column can be checked using `dtype`."
    - "Make conscious decisions about how to manage missing data."
    - "A DataFrame can be saved to a CSV file using the `to_csv` function."
---

# What is NetCDF?
## Gridded data
These lessons work with raster or “gridded” data that are stored as a uniform grid of values using the netCDF file format. This is the most common data format and file type in the atmosphere and ocean sciences; essentially all output from weather, climate and ocean models is gridded data stored as a series of netCDF files.

## Advantages




# Storage of netCDF data
The data in a netCDF file is stored in the form of arrays. For example, temperature varying over time at a location is stored as a one-dimensional array. Temperature over an area for a given time is stored as a two-dimensional array.

Three-dimensional (3D) data, like temperature over an area varying with time, or four-dimensional (4D) data, like temperature over an area varying with time and altitude, is stored as a series of two-dimensional arrays.


# Basic components of a netCDF file
A netCDF file contains dimensions, variables, and attributes. These components are used together to capture the meaning of data and relations among data fields in an array-oriented dataset. The following figure shows the structure of a netCDF file using the CDL (network Common Data form Language) notation. CDL is the ASCII format used to describe the content of a netCDF file.

## Dimensions

A netCDF dimension has both a name and a size. A dimension size is an arbitrary positive integer. Only one dimension in a netCDF file can have the size UNLIMITED. Such a dimension is the unlimited dimension or record dimension. A variable with an unlimited dimension can grow to any length along that dimension.

A dimension can be used to represent a real physical dimension, for example, time, latitude, longitude, or height. A dimension can also be used to index other quantities, for example, station or model run number. It is possible to use the same dimension more than once in specifying a variable shape.
Variables

A variable represents an array of values of the same type. Variables are used to store the bulk of the data in a netCDF file. A variable has a name, data type, and shape described by its list of dimensions specified when the variable is created. The number of dimensions is the rank (also known as dimensionality). A scalar variable has a rank of 0, a vector has a rank of 1, and a matrix has a rank of 2. A variable can also have associated attributes that can be added, deleted, or changed after the variable is created.

## Coordinate variables

A one-dimensional variable with the same name as a dimension is a coordinate variable. It is associated with a dimension of one or more data variables and typically defines a physical coordinate corresponding to that dimension.

Coordinate variables have no special meaning to the netCDF library. However, the software using this library should handle coordinate variables in a specialized way.

## Attributes

NetCDF attributes are used to store ancillary data or metadata. Most attributes provide information about a specific variable. These attributes are identified by the name of the variable together with the name of the attribute.

Attributes that provide information about the entire netCDF file are global attributes. These attributes are identified by the attribute name together with a blank variable name (in CDL) or a special null variable ID (in C or Fortran).






# What tools to use NetCDF with
Python: two packages mainly used are xarray and iris. The following lessons are using xarray which has a syntax very comaparable to pandas, so same principles can be used.

Can use ncdump to look at the metadata without opening a notebook (

Ivan recommende keeping a small part of vectorisatio in there (like multiplication or addition) to touch on the strength of xarray, a for loop would blow up your computer.

Ivan slices and subsets is datasets before loading it into xarray. 

# CMIP data
This is the dataset that we will be using for our class and is very known and widely used by oceanographers
