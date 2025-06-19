---
title: 'NebulaTextures: A Stellarium Plugin for Custom Deep-Sky Textures and Online Astrometric Registration'
tags:
  - astronomy
  - Stellarium
  - planetarium software
  - astrophotography
  - image processing
  - plate-solving
  - plugin
  - world coordinate system
authors:
  - name: WANG Siliang
    affiliation: "1, 2"
    orcid: 0009-0000-2376-0115
    email: cencrx@outlook.com
affiliations:
 - name: Zhanjiang Administration College, Guangdong, China
   index: 1
 - name: Huazhong University of Science and Technology, Hubei, China
   index: 2
   ror: 00p991c53
date: 18 May 2025
bibliography: paper.bib
---

# Summary

# Statement of Need

While Stellarium provides an expansive and curated catalog of built-in nebula and DSO textures, it lacks native support for user-defined, dynamically inserted visual assets. The manual process of aligning astrophotographs or drawings to celestial coordinates is technically demanding and error-prone, with limited user interface support. As a result, even experienced users often refrain from customizing their Stellarium installations.

This work presents NebulaTextures, a plugin that addresses this gap by offering an intuitive workflow for image import, automatic astrometric registration, and seamless integration into Stellarium’s rendering engine. It empowers users to easily enhance their Stellarium experience with their own visual contributions.

# Astronomical Context

Accurately placing astronomical images in a virtual sky relies on celestial coordinates, Right Ascension (RA) and Declination (Dec). Many images include WCS (World Coordinate System) data in their FITS headers, mapping pixel positions to sky coordinates. To obtain this mapping when absent, **astrometric registration** (or plate-solving) analyzes star patterns in the image and matches them to catalogs. The plugin automates this process via the [Astrometry.net](https://astrometry.net/) service, enabling precise sky alignment for user-submitted images.

# System Design

NebulaTextures integrates with Stellarium using its established plugin infrastructure. The plugin's design is modular, with key components handling specific tasks:

| **Component**          | **Purpose**                                                  |
| ---------------------- | ------------------------------------------------------------ |
| `NebulaTextures`       | Core plugin controller, manages hooks, rendering calls, and state |
| `NebulaTexturesDialog` | Provides the graphical user interface for user interaction, preview, and configuration |
| `PlateSolver`          | Handles communication with the Astrometry.net API, submitting images and processing results |
| `SkyCoords`            | Manages WCS transformations and the logic for projecting pixel coordinates to celestial positions |
| `TextureConfigManager` | Responsible for parsing and managing the JSON-based configuration files that define texture groups and properties |
| `TileManager`          | Loads, blends, and displays textures using Stellarium’s internal tile system for efficient rendering |



The typical workflow for a user integrating an image is as follows chart:

![Figure 1: User image integration workflow of NebulaTextures Plugin](flowchart.pdf)

# Astrometric Algorithms


# Applications


# Acknowledgements

We thank the Stellarium team for their extensible plugin framework and their thoughtful guidance provided in the pull request, and the Astrometry.net project for their essential plate-solving service.

# References
