# Web Development Code Examples

## HTML Example

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Sample Page</title>
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <div class="container">
      <h1>Hello World</h1>
      <button id="btnClick">Click Me</button>
    </div>

    <script src="app.js"></script>
  </body>
</html>
```

---

## CSS Example

```css
body {
  margin: 0;
  font-family: Arial, sans-serif;
  background-color: #f5f5f5;
}

.container {
  padding: 20px;
  text-align: center;
}

button {
  padding: 10px 20px;
  cursor: pointer;
}
```

---

## SCSS Example

```scss
$primary-color: #3498db;
$border-radius: 8px;

.container {
  padding: 20px;

  .card {
    background: white;
    border-radius: $border-radius;
    padding: 16px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);

    h2 {
      color: $primary-color;
    }

    button {
      background: $primary-color;
      color: white;
      border: none;
      padding: 10px 15px;
      border-radius: $border-radius;

      &:hover {
        opacity: 0.9;
      }
    }
  }
}
```

---

## JavaScript Example

```javascript
document.addEventListener("DOMContentLoaded", () => {
  const button = document.getElementById("btnClick");

  button?.addEventListener("click", () => {
    alert("Button clicked!");
  });
});

function add(a, b) {
  return a + b;
}

console.log(add(10, 20));
```

---

## TypeScript Example

```typescript
interface User {
  id: number;
  name: string;
  email: string;
}

class UserService {
  private users: User[] = [];

  addUser(user: User): void {
    this.users.push(user);
  }

  getUsers(): User[] {
    return this.users;
  }
}

const service = new UserService();

service.addUser({
  id: 1,
  name: "John Doe",
  email: "john@example.com",
});

console.log(service.getUsers());
```

---

## Project Structure

```text
project/
├── index.html
├── css/
│   ├── styles.css
│   └── styles.scss
├── js/
│   └── app.js
├── ts/
│   └── app.ts
└── assets/
    ├── images/
    └── fonts/
```

---

## TypeScript Compilation

```bash
npm install -g typescript

tsc app.ts
```

---

## SCSS Compilation

```bash
npm install -g sass

sass styles.scss styles.css
```
