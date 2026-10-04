The important distinction is between:

- RoxTrackCircuits knowing about RoxRouting, and
- RoxTrackCircuits knowing about an interface which RoxRouting happens to implement.
  
You want the latter.

## The dependency you want

Conceptually:

             implements
RoxRouting ───────────────► RoxTrackCircuitsListener
    │
    │ uses
    ▼
RoxTrackCircuits

But RoxTrackCircuits itself should not include or know about RoxRouting.

So you could have:

```
class RoxTrackCircuitsListener
{
public:
    virtual void trackCircuitEvent(...) = 0;
};
```

Then:

```
class RoxTrackCircuits
{
public:
    void setListener(RoxTrackCircuitsListener* listener);

private:
    RoxTrackCircuitsListener* listener;
};
```

And:

```
class RoxRouting : public RoxTrackCircuitsListener
{
    ...
};
```

RoxRouting can then call methods on RoxTrackCircuits, while RoxTrackCircuits can call back through the interface.

Then, once all the objects exist, connect them:

```
roxTrackCircuits.setListener(&roxRouting);
```

You could do that in the RoxOcsPanel constructor body.

In fact, I'd be inclined to make RoxRouting do it, since it is the thing that wants to receive track-circuit events:

'''
RoxRouting::RoxRouting(
    RoxSignals* signals,
    RoxPoints* points,
    RoxTrackCircuits* trackCircuits)
    :
    signals(signals),
    points(points),
    trackCircuits(trackCircuits)
{
    trackCircuits->setListener(this);
}
'''

Then your panel doesn't need to know about the connection at all.