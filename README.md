# React Native Dimensions API: Initial Dimensions Inconsistent

This repository demonstrates a common issue when using the `Dimensions` API in React Native to get screen dimensions.  The problem arises because the dimensions aren't always immediately available during initial rendering, leading to layout inconsistencies.  This example shows the problem and provides a solution using the `Dimensions.addEventListener` method to monitor changes and `useEffect` hook for cleanup.

## Problem

The synchronous `Dimensions.get('window')` method may return inaccurate dimensions if called too early in the component lifecycle.  This leads to incorrect rendering, particularly noticeable on app launch or after orientation changes.

## Solution

The solution uses `Dimensions.addEventListener` to listen for dimension changes and updates the component state accordingly.  The `useEffect` hook ensures proper cleanup to avoid memory leaks.