# Database Migration Tool

A simple JavaScript package for managing database migrations in Node.js applications.

## Installation

You can install the Database Migration Tool via npm:

```bash
npm install database-migration-tool
```

## Usage

```javascript
const MigrationTool = require('database-migration-tool');

// Create an instance of MigrationTool with database connection options
const migrationTool = new MigrationTool({
  db: /* Your database connection */,
  migrationsDir: './migrations' // Optional: specify the directory containing migration files
});

// Migrate the database
migrationTool.migrate()
  .then(() => console.log('Database migration completed successfully'))
  .catch(error => console.error('Error migrating database:', error));
```

## Migration Files

Migration files are JavaScript files that export objects with `up` and optionally `down` methods, responsible for applying and reverting the migration, respectively. Place your migration files in a directory (default: `./migrations`).

Example migration file (`./migrations/migration_1.js`):

```javascript
module.exports = {
  async up(db) {
    // Database-specific code to apply the migration
  },
  
  async down(db) {
    // Database-specific code to revert the migration
  }
};
```

## License

This package is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
