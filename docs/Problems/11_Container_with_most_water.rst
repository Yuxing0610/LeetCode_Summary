=======================================================
11. Container with most water
=======================================================

General Idea
============

use double pointer and move the one points to shorter bar, becasue if you don't move this, then the volumn of the container can no longer increase.

Python Code
=============

.. code-block:: python

    
    #Simple double pointer problem
    class Solution(object):
        def maxArea(self, height):
            """
            :type height: List[int]
            :rtype: int
            """
            res = 0
            i = 0
            j = len(height) - 1
            while i<j:
                cur = (j-i)*min(height[i], height[j])
                if cur > res:
                    res = cur
                if height[i] <= height[j]:
                    i = i+1
                else:
                    j = j-1
            return res