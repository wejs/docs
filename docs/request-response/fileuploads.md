# File uploads

See we-plugin-file: https://github.com/wejs/we-plugin-file

## Amazon s3 configuration example:

/**
 * Amazon S3 upload configuration example
 *
 * Set secret and access key in system env or in project config/local.js file like:
 * process.env.AWS_ACCESS_KEY_ID = 'acceskey'
 * process.env.AWS_SECRET_ACCESS_KEY = 'secret'
 *
 */

var uuid = require('node-uuid')
var s3 = require('multer-storage-s3')

module.exports.upload = {
  storages: {

    //
    // - Generic file upload
    //

    s3File: {
      // required for redirect from download url to S3 url
      isLocalStorage: false,
      // get file url from location
      getUrlFromFile: function (format, file, done) {
        // (optional) save extraData on create
        if (!file.extraData) file.extraData = file.s3
        // return the permanent file url for this format
        // in this example we are returning the original path for generic file uploads
        return file.s3.Location
      },
      storage: s3({
        destination: function (req, file, cb) {
          // path inside s3 bucket
          cb(null, 'wejs-uploads/files')
        },
        filename: function (req, file, cb) {
          // set file name
          // i like uuid in file names
          file.name = Date.now() + '_' + uuid.v1() + '.'
          // set extension
          file.name += (file.originalname.split('.').pop())
          // return the file name in callback to se it in S3
          cb(null, file.name)
        },
        // bucket and region:
        bucket: 'wejs-files',
        region: 'us-east-1'
      })
    },

    //
    // - Image upload
    //

    s3Image: {
      // required for redirect from download url to S3 url
      isLocalStorage: false,
      // get file url from location
      getUrlFromFile: function (format, file, done) {
        // (optional) save extraData on create
        if (!file.extraData) file.extraData = file.s3
        // return the permanent file url for this format
        // in this example we are returning the original path for generic file uploads
        return file.s3.Location
      },
      storage: s3({
        destination: function (req, file, cb) {
          // path inside s3 bucket
          cb(null, 'wejs-uploads/images')
        },
        filename: function (req, file, cb) {
          // set file name
          // i like uuid in file names
          file.name = Date.now() + '_' + uuid.v1() + '.'
          // set extension
          file.name += (file.originalname.split('.').pop())
          // return the file name in callback to se it in S3
          cb(null, file.name)
        },
        // bucket and region:
        bucket: 'wejs-files',
        region: 'us-east-1'
      })
    }
  }
}
