# Material 3 Navigation Drawer In Sketchware Pro
[![Click to watch the video](https://img.youtube.com/vi/VIDEO_ID_HERE/0.jpg)](https://www.youtube.com/watch?v=VIDEO_ID_HERE)
---

## 🧭 Comprehensive Navigation Drawer Java Attributes Guide

This table details the essential Java attributes, methods, and concepts used to interact with the **Material 3 Navigation Drawer**, typically implemented using `androidx.drawerlayout.widget.DrawerLayout` (the container) and `com.google.android.material.navigation.NavigationView` (the menu view).

| Attribute/Method | Class | Type | Description | Example Usage |
| :--- | :--- | :--- | :--- | :--- |
| **`DrawerLayout`** | `androidx.drawerlayout.widget.DrawerLayout` | View | The root layout that holds both the main content and the movable drawer pane(s). | `DrawerLayout drawerLayout = findViewById(R.id.drawer_layout);` |
| **`NavigationView`** | `com.google.android.material.navigation.NavigationView` | View | The view that displays the navigation menu items, header, and footer. | `NavigationView navigationView = findViewById(R.id.nav_view);` |
| **`openDrawer(int gravity)`** | `DrawerLayout` | Method | Programmatically opens the drawer specified by gravity (e.g., `GravityCompat.START`). | `drawerLayout.openDrawer(GravityCompat.START);` |
| **`closeDrawer(int gravity)`** | `DrawerLayout` | Method | Programmatically closes the drawer specified by gravity. | `drawerLayout.closeDrawer(GravityCompat.START);` |
| **`isDrawerOpen(int gravity)`** | `DrawerLayout` | Method | Checks if the drawer at the given gravity is currently open. | `if (drawerLayout.isDrawerOpen(GravityCompat.START)) { ... }` |
| **`setDrawerLockMode(int lockMode)`** | `DrawerLayout` | Method | Controls the ability to open and close the drawer by touch gestures. Lock modes include `LOCK_MODE_UNLOCKED`, `LOCK_MODE_LOCKED_CLOSED`, and `LOCK_MODE_LOCKED_OPEN`. | `drawerLayout.setDrawerLockMode(DrawerLayout.LOCK_MODE_LOCKED_CLOSED);` |
| **`setScrimColor(int color)`** | `DrawerLayout` | Method | Sets the color of the protective overlay (scrim) that appears over the main content when the drawer is open. | `drawerLayout.setScrimColor(Color.parseColor("#40000000"));` |
| **`setNavigationItemSelectedListener(listener)`** | `NavigationView` | Method | Attaches a listener to handle click events on the menu items within the drawer. | `navigationView.setNavigationItemSelectedListener(this);` |
| **`onNavigationItemSelected(MenuItem item)`** | `NavigationView.OnNavigationItemSelectedListener` | Callback | The required callback method in the listener, triggered when a menu item is tapped. | `@Override public boolean onNavigationItemSelected(MenuItem item) { // Handle click }` |
| **`getMenu()`** | `NavigationView` | Method | Retrieves the `Menu` object, allowing for dynamic changes to menu items (e.g., hiding, showing, or accessing item IDs). | `Menu menu = navigationView.getMenu();` |
| **`getMenuItemId()`** | `MenuItem` | Method | Gets the unique resource ID of the selected or accessed menu item. | `int id = item.getItemId();` |
| **`getCheckedItem()`** | `NavigationView` | Method | Returns the currently selected/checked `MenuItem`. Useful for restoring state or highlighting the active screen. | `MenuItem checkedItem = navigationView.getCheckedItem();` |
| **`setCheckedItem(int id)`** | `NavigationView` | Method | Programmatically sets a menu item as checked/selected. | `navigationView.setCheckedItem(R.id.nav_home);` |
| **`getHeaderView(int index)`** | `NavigationView` | Method | Gets a specific header view added to the navigation drawer. Index is usually `0`. | `View headerView = navigationView.getHeaderView(0);` |
| **`findViewById(int id)`** | `View` (on Header) | Method | Used on the retrieved header view to find and manipulate components within the header layout (e.g., an `ImageView` or `TextView`). | `TextView username = headerView.findViewById(R.id.username);` |
| **`Menu.findItem(int id)`** | `Menu` | Method | Finds a specific `MenuItem` by its ID within the menu. Essential for badge updates. | `MenuItem badgeItem = menu.findItem(R.id.nav_messages);` |
| **`MenuItem.setActionView(View view)`** | `MenuItem` | Method | Programmatically sets a custom view for the menu item. This is the common way to add a dynamic **Badge**. | `badgeItem.setActionView(badgeTextView);` |
| **`GravityCompat.START`** | `androidx.core.view.GravityCompat` | Constant | The standard constant for a left-to-right (LTR) start-aligned drawer (the left side). | `drawerLayout.openDrawer(GravityCompat.START);` |
| **`GravityCompat.END`** | `androidx.core.view.GravityCompat` | Constant | The standard constant for an end-aligned drawer (the right side). | `drawerLayout.openDrawer(GravityCompat.END);` |

---

## ➕ Features

* **Material 3 Design:** Implements the latest Google Material Design guidelines for a modern look and feel.
* **Navigation Badges:** Demonstrates how to add and manage expressive badges dynamically on navigation drawer items using `MenuItem.setActionView()`.
* **60+ Sketchware Pro Blocks:** Includes a comprehensive set of free, ready-to-use blocks to quickly integrate and customize the drawer functionality in your projects, handling both drawer control and menu item management.

## 🛠️ Implementation Notes

* **`fitsSystemWindows` for Full Screen:** You must ensure that `android:fitsSystemWindows="true"` is set on the root layout (`_drawer_main` or your equivalent) of your `NavigationView` to ensure it extends properly under the system status bar, providing a modern, full-screen look.
    * **Check XML Command Manager:** Click the 3-dot menu > **XML Command Manager**.
    * **Also Resource Manager:** Check `menu/` and your drawer layout XML.
* **Layout ID Uniqueness:** Make sure all layout IDs (e.g., `TextView`, `ImageView` IDs) are **unique** across your main activity, drawer header, and badge layouts. Duplicate IDs can lead to view conflicts and crashes.

---

## 📜 License

**Open & Free (No Restrictions)**

This project is released as **CC0 1.0 Universal**. You are free to use, modify, and share it for any purpose, including commercial projects—**no attribution required, no restrictions**.

### Third-Party Libraries

This project may include third-party libraries (e.g., Material Components, AppCompat). Each library is subject to its own license (e.g., Apache 2.0). Please review their licenses if you plan to use them.
