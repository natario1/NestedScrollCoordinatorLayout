# NestedScrollCoordinatorLayout

```groovy
compile 'com.otaliastudios:nestedscrollcoordinatorlayout:1.0.2'
```

A `CoordinatorLayout` that implements nested scrolling and propagates scroll events to parent views.
This is useful for nested Coordinators, e.g. for inner fragments in a parent activity. 
By default, scroll events that take place inside the inner `CoordinatorLayout` won't reach the outer 
coordinator, and thus they won't trigger scroll animations and so on.

If `NestedScrollCoordinatorLayout` is used, events are correctly propagated.

## Usage

Just use `NestedScrollCoordinatorLayout` as the inner `CoordinatorLayout`.

```xml
<!-- parent coordinator -->
<android.support.design.widget.CoordinatorLayout
    android:layout_width="match_parent"
    android:layout_height="match_parent">
    
    <!-- stuff... -->
    
    <!-- inner coordinator with stuff inside -->
    <com.otaliastudios.nestedscrollcoordinatorlayout.NestedScrollCoordinatorLayout
        android:layout_width="match_parent"
        android:layout_height="match_parent"/>   
    
</android.support.design.widget.CoordinatorLayout>
```

You can have slight control over the scroll propagation behavior using
`NestedScrollCoordinatorLayout.setPassMode()`. Specifically:

- `PASS_MODE_BOTH` (default): scroll events are passed to the parent stream and, at the same time,
to this Coordinator childs
- `PASS_MODE_PARENT_FIRST`: scroll events are passed to the parent stream and, if not consumed,
they go on to this Coordinator childs

## Contributing

You are welcome to contribute with issues, PRs or suggestions.
