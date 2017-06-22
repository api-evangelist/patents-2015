---

title: Using a depth map of a monitored scene to identify floors, walls, and ceilings
abstract: A process identifies large planar surfaces in scenes. The process receives captured IR images of a scene taken by a 2-dimensional array of image sensors of a camera system. Each IR image is captured when a distinct subset of IR illuminators of the camera system is illuminated. The process constructs a depth map of a scene using IR images and uses the depth map to compute a binary depth edge map for the scene. The binary depth edge map identifies which points in the depth map comprise depth discontinuities. The process identifies contiguous components based on the binary depth edge map and determines that a first component of the contiguous components represents a large planar surface in the scene by: fitting a plane to points in the first component; determining the orientation of the plane; and determining that the plane fitting residual error is less than a predefined threshold.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09613423&OS=09613423&RS=09613423
owner: 
number: 09613423
owner_city: 
owner_country: 
publication_date: 20150612
---
