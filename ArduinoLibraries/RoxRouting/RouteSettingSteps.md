# Route Setting Steps

## Step 0

The route is idle, with no setting or cancelling in progress.

## Step 1

The route availability is checked. If not available, the step is moved back to 1. If available, the step moves on to 2.

## Steps 2, 4, 6, 8, 10, 12, 14, 16, 18 and 20

Each of these steps will instruct a set of points to move to the correct position. This allows for up to ten sets of points to be included in any route. Once the instruction has been sent, the step will move on to the next number - for example from 2 to 3, or from 4 to 5.

If at any point in processing the list, a point number of zero is found, that is an indication that the route has no more points to set, so the next step in taht case will be set to 22.

## Steps 3, 5, 7, 9, 11, 13, 15, 17, 19 and 21

Each of these steps will wait for confirmation that the points instructed to move in the previous step have now moved to the correct position.

Once confirmation is received, the next step will be set to the next number - for example from 3 to 4, or from 5 to 6. Note that if a route has the maximum of ten points, then the next step from 21 will be 22 meaning that no special processing is required.