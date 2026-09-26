# Route Setting Steps

## Step 0

The route is idle, with no setting or cancelling in progress.

## Step 1

The route availability is checked. If not available, the step is moved back to 1. If available, the step moves on to 2.

## Step 2

This step will work through each set of points in the route in turn. A counter on the route will show which set of points is being dealt with. A flag will indicate whether the points have been asked to move (and hence a report of detection is awaited).

Once confirmation of movement has been received, the next set of points will be processed.

If at any point in processing the list, a point number of zero is found, that is an indication that the route has no more points to set, so the next step in that case will be set to 3.

## Step 3

