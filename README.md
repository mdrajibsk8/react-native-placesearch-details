{
  "name": "react-native-placesearch",
  "version": "4.0.0",
  "description": "A simple package where you can easily search google places and customize package ui",
  "main": "lib/commonjs/index",
  "module": "lib/module/index",
  "types": "lib/typescript/index.d.ts",
  "react-native": "src/index",
  "source": "src/index",
  "files": [
    "src",
    "lib",
    "android",
    "ios",
    "cpp",
    "react-native-placesearch.podspec",
    "!lib/typescript/example",
    "!android/build",
    "!ios/build",
    "!**/__tests__",
    "!**/__fixtures__",
    "!**/__mocks__"
  ],
  "scripts": {
    "test": "jest",
    "typescript": "tsc --noEmit",
    "lint": "eslint \"**/*.{js,ts,tsx}\"",
    "prepare": "bob build",
    "release": "release-it",
    "example": "yarn --cwd example",
    "pods": "cd example && pod-install --quiet",
    "bootstrap": "yarn example && yarn && yarn pods"
  },
  "keywords": [
    "react-native",
    "react-native-placesearch",
    "react-native-google-place-autocomplete",
    "react-native-google-place-search",
    "react-native-place-search-google"
  ],
  "repository": "https://github.com/mdrajibsk8/react-native-placesearch-details/tree/main",
  "author": "mdrajibsk8 <mdrajibsk8@gmail.com> (https://github.com/mdrajibsk8)",
  "license": "MIT",
  "bugs": {
    "url": "https://github.com/mdrajibsk8/react-native-placesearch-details/tree/main"
  },
  "homepage": "https://github.com/mdrajibsk8/react-native-placesearch-details/tree/main",
  "publishConfig": {
    "registry": "https://registry.npmjs.org/"
  },
  "devDependencies": {
    "@commitlint/config-conventional": "^11.0.0",
    "@react-native-community/eslint-config": "^2.0.0",
    "@release-it/conventional-changelog": "^2.0.0",
    "@types/jest": "^26.0.0",
    "@types/react": "^16.9.19",
    "@types/react-native": "0.62.13",
    "commitlint": "^11.0.0",
    "eslint": "^7.2.0",
    "eslint-config-prettier": "^7.0.0",
    "eslint-plugin-prettier": "^3.1.3",
    "husky": "^6.0.0",
    "jest": "^26.0.1",
    "pod-install": "^0.1.0",
    "prettier": "^2.0.5",
    "react": "16.13.1",
    "react-native": "0.63.4",
    "react-native-builder-bob": "^0.18.0",
    "release-it": "^14.2.2",
    "typescript": "^4.1.3"
  },
  "peerDependencies": {
    "react": "*",
    "react-native": "*"
  },
  "jest": {
    "preset": "react-native",
    "modulePathIgnorePatterns": [
      "<rootDir>/example/node_modules",
      "<rootDir>/lib/"
    ]
  },
  "commitlint": {
    "extends": [
      "@commitlint/config-conventional"
    ]
  },
  "release-it": {
    "git": {
      "commitMessage": "chore: release ${version}",
      "tagName": "v${version}"
    },
    "npm": {
      "publish": true
    },
    "github": {
      "release": true
    },
    "plugins": {
      "@release-it/conventional-changelog": {
        "preset": "angular"
      }
    }
  },
  "eslintConfig": {
    "root": true,
    "extends": [
      "@react-native-community",
      "prettier"
    ],
    "rules": {
      "prettier/prettier": [
        "error",
        {
          "quoteProps": "consistent",
          "singleQuote": true,
          "tabWidth": 2,
          "trailingComma": "es5",
          "useTabs": false
        }
      ]
    }
  },
  "eslintIgnore": [
    "node_modules/",
    "lib/"
  ],
  "prettier": {
    "quoteProps": "consistent",
    "singleQuote": true,
    "tabWidth": 2,
    "trailingComma": "es5",
    "useTabs": false
  },
  "react-native-builder-bob": {
    "source": "src",
    "output": "lib",
    "targets": [
      "commonjs",
      "module",
      [
        "typescript",
        {
          "project": "tsconfig.build.json"
        }
      ]
    ]
  },
  "dependencies": {
    "@react-native-community/cli": "^6.1.0",
    "@react-native-community/toolbar-android": "^0.2.1",
    "native-base": "^2.13.8"
  }
}
