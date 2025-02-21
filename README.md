# React Router v6 Wildcard Route Order Issue

This repository demonstrates a subtle bug in React Router v6 related to the order of wildcard routes (`/*`).  When a more specific route and a wildcard route are defined, the order can unexpectedly affect which route is matched.

## The Problem

In the example provided, a wildcard route (`/*`) is placed after the `/about` route.  This means the wildcard route will always match, preventing the `/about` route from ever being activated.

## Solution

To fix this, the wildcard route must be placed *before* any more specific routes within the `<Routes>` component. This ensures that more specific routes are matched before the wildcard acts as a fallback.